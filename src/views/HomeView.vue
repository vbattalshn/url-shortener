<template>
  <Header />
  <div class="content">
    <h2 class="content-title">
      Simple links for <span class="Higlight-text">everyone.</span>
      <div v-if="isError" v-text="errorMsg" class="error-msg"></div>
    </h2>
    <div class="input-hero">
      <input
        type="text"
        class="input"
        id="url"
        placeholder="https://www.google.com/"
        v-model="url"
        v-if="!isShorten"
      />
      <input
        v-else
        type="text"
        class="input"
        id="shortUrl"
        :value="shortenUrl"
        :disabled="isDisabled"
      />
      <button v-if="isShorten" @click="Share" class="button share">
        Share <Icon icon="share" />
      </button>
      <button v-if="isShorten" @click="Copy" class="button copy">
        Copy <Icon icon="copy" />
      </button>
      <button v-if="isShorten" @click="Again" class="button">
        Again <Icon icon="again" />
      </button>
      <button v-if="!isShorten && !isSpinner" @click="Shorten" class="button">
        Shorten <Icon icon="arrow-right" />
      </button>
      <button v-if="isSpinner" class="button spinner"></button>
    </div>
    <div class="content-background">
      <Icon icon="background" />
    </div>
  </div>
</template>

<script>
import Header from "../components/Header";
import Icon from "../components/Icon";
import axios from "axios";

export default {
  components: { Header, Icon },
  data() {
    return {
      url: "https://battalsahin.com/",
      shortenUrl: "asdasd",
      isShorten: false,
      isSpinner: false,
      isError: false,
      errorMsg: "",
      inputClass: "",
      isDisabled: true,
    };
  },
  methods: {
    Shorten() {
      if (this.validURL(this.url)) {
        this.isSpinner = true;
        this.isError = false;
        this.errorMsg = "";

        let data = {
          url: this.url,
        };

        axios
          .post(this.$store.state.baseApi + "?action=short", data)
          .then((response) => {
            console.log(response.data);
            if (response.data.success) {
              this.shortenUrl =
                window.location.hostname +
                (window.location.port ? ":" + window.location.port : "") +
                "/go/" +
                response.data.token;
            } else {
              this.isError = true;
              this.errorMsg = response.data.message;
            }
            this.isSpinner = false;
            this.isShorten = true;
          })
          .catch((error) => {
            alert(error);
          });
      } else {
        this.isError = true;
        this.errorMsg = "Please enter a valid url";
      }
    },
    Again() {
      this.url = "";
      this.shortenUrl = "asdasd";
      this.isSpinner = false;
      this.isShorten = false;
      this.isDisabled = true;
    },
    Copy() {
      var copyText = document.getElementById("shortUrl");

      copyText.select();
      copyText.setSelectionRange(0, 99999);

      if (navigator && navigator.clipboard && navigator.clipboard.writeText) {
        navigator.clipboard.writeText(copyText.value);
        alert("Copied");
      } else {
        alert("Failed to copy try manually");
        this.isDisabled = false;
      }
    },
    validURL(str) {
      var pattern = new RegExp(
        "^(https?:\\/\\/)?" +
          "((([a-z\\d]([a-z\\d-]*[a-z\\d])*)\\.)+[a-z]{2,}|" +
          "((\\d{1,3}\\.){3}\\d{1,3}))" +
          "(\\:\\d+)?(\\/[-a-z\\d%_.~+]*)*" +
          "(\\?[;&a-z\\d%_.~+=-]*)?" +
          "(\\#[-a-z\\d_]*)?$",
        "i"
      );
      return !!pattern.test(str);
    },
    Share() {
      let shareData = {
        title: "Short Url",
        text: "We shortened a long url for you",
        url: this.shortenUrl,
      };

      if (!navigator.canShare) {
        alert("navigator.canShare() not supported.");
      } else if (navigator.canShare(shareData)) {
        navigator.share(shareData);
      } else {
        alert("Specified data cannot be shared.");
      }
    },
  },
};
</script>

<style>
.content {
  margin: 10px;
  padding: 20px;
  display: flex;
  align-items: flex-start;
  justify-content: center;
  flex-direction: column;
  overflow: hidden;
  height: calc(100vh - 100px);
  width: calc(100% - 20px);
  background: linear-gradient(
    180deg,
    #f5fdff 38.02%,
    rgba(245, 253, 255, 0) 100%
  );
  border-radius: 20px;
  position: relative;
  gap: 20px;
}

.content-background {
  position: absolute;
  top: 0;
  right: 0;
}

.content-title {
  font-size: 2.5rem;
  font-weight: 500;
}

.Higlight-text {
  font-weight: 600;
  display: block;
  color: var(--brand-color);
  text-decoration: underline;
}

.input-hero {
  display: flex;
  justify-content: center;
  width: calc(100% - 6rem);
  box-shadow: 0px 4px 4px rgb(128 128 128 / 25%);
  border-radius: 0.75rem;
}

.input {
  height: 3.5rem;
  font-size: 1rem;
  flex: 1;
  padding: 15px;
  background: var(--white);
  border: none;
  border-radius: 0.75rem 0 0 0.75rem;
  transition: all 0.25s ease 0s;
}

.button.copy,
.button.share {
  border-radius: 0;
}

.button.copy {
  background: var(--green);
}

.button.share {
  background: var(--focus);
}

.button {
  font-size: 1rem;
  font-weight: 500;
  padding: 15px;
  background: var(--brand-color);
  border: none;
  border-radius: 0 0.75rem 0.75rem 0;
  transition: all 0.25s ease 0s;
  color: var(--white);
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 5px;
}

@media screen and (max-width: 768px) {
  .input-hero {
    width: 100%;
    flex-direction: column;
    gap: 10px;
    box-shadow: none;
    border-radius: none;
  }
  .content-background {
    display: none;
  }
  .button,
  .button.share,
  .button.copy,
  .input {
    border-radius: 0.75rem;
    box-shadow: 0px 4px 4px rgb(128 128 128 / 25%);
  }
}

.input.error {
  box-shadow: 0 0 0 3px var(--red);
}

@media screen and (max-height: 500px) {
  .content-background {
    display: none;
  }
}

.error-msg {
  padding: 20px 0 0 0;
  font-size: 1.15rem;
  font-weight: 500;
  color: var(--red);
}
</style>
