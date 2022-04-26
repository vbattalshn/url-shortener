<template>
  <div class="page-hero center">
    <div v-if="noSsl" class="alert-popup">
      <div class="alert-icon">
        <Icon icon="danger" />
      </div>
      <div class="alert-msg">
        The site you are directed to does not have an ssl certificate. Do you
        still want to continue?
      </div>
      <div class="alert-btns">
        <button class="alert-btn btn" @click="Continue()">Continue</button>
        <button class="back-btn btn" @click="Back()">Turn back</button>
      </div>
    </div>
  </div>
</template>

<script>
import Icon from "../components/Icon";

export default {
  components: { Icon },
  data() {
    return {
      token: this.$route.params.token,
      url: "",
      noSsl: false,
    };
  },
  mounted() {
    if (this.token == "" || this.token == null) {
      this.$router.push("/");
    }

    let data = {
      token: this.token,
    };

    this.axios
      .post(this.$store.state.baseApi + "/?action=getUrl", data)
      .then((response) => {
        console.log(response.data);
        if (response.data.success) {
          this.url = response.data.url;
          if (this.url.slice(0, 8) == "https://") {
            window.location.replace(response.data.url);
          } else {
            this.noSsl = true;
            setTimeout(() => {
              window.location.replace(response.data.url);
            }, 10000);
          }
        } else {
          alert(response.data.message);
        }
      })
      .catch((error) => {
        alert(error);
        this.$router.push("/");
      });
  },
  methods: {
    Continue() {
      window.location.replace(this.url);
    },
    Back() {
      this.$router.go(-1);
    },
  },
};
</script>

<style>
.center {
  width: 100%;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.alert-popup {
  max-width: 450px;
  height: auto;
  width: 90%;
  padding: 20px;
  border-radius: 20px;
  background: #e0e0e0;
  box-shadow: 0 5px 5px #80808080;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  gap: 20px;
  animation: openAnom 0.25s ease forwards;
}

@keyframes openAnom {
  0% {
    transform: scale(0.8);
  }
  100% {
    transform: scale(1);
  }
}

.alert-msg {
  font-size: 1rem;
  font-weight: 500;
  color: var(--color);
  text-align: center;
}

.alert-popup .btn {
  flex: 1;
  padding: 15px 10px;
  font-size: 1rem;
  font-weight: 500;
  border-radius: 20px;
  border: 0;
}

.alert-btns {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 20px;
  width: 100%;
}

button.alert-btn.btn {
  background: var(--red-trns);
  color: var(--white);
  box-shadow: 0 5px 5px var(--red-trns);
  position: relative;
  overflow: hidden;
}

button.back-btn.btn {
  background: transparent;
  color: #426bfe;
}

button.alert-btn.btn:focus {
  box-shadow: 0 5px 5px var(--red-trns), 0 0 0 3px var(--focus-trns);
}

button.alert-btn.btn:after {
  content: "";
  height: 100%;
  width: 0px;
  position: absolute;
  top: 0;
  left: 0;
  background: var(--red);
  z-index: -1;
  animation: timerAnim 10s linear forwards;
}

@keyframes timerAnim {
  100% {
    width: 100%;
  }
}
</style>
