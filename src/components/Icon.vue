<template>
    <svg v-if="icon == 'logo'" width="35" height="35" viewBox="0 0 35 35" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M21.9437 25.0417H24.1458C28.55 25.0417 32.1666 21.4396 32.1666 17.0208C32.1666 12.6167 28.5646 9 24.1458 9H21.9437" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M13.2083 9H11.0208C6.60208 9 3 12.6021 3 17.0208C3 21.425 6.60208 25.0417 11.0208 25.0417H13.2083" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M11.75 17.0208H23.4167" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>
    <svg v-else-if="icon == 'profile-circle'" width="35" height="35" viewBox="0 0 35 35" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M17.675 18.6375C17.5729 18.6229 17.4416 18.6229 17.325 18.6375C14.7583 18.55 12.7166 16.45 12.7166 13.8688C12.7166 11.2292 14.8458 9.08542 17.5 9.08542C20.1396 9.08542 22.2833 11.2292 22.2833 13.8688C22.2687 16.45 20.2416 18.55 17.675 18.6375Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M27.3292 28.2625C24.7333 30.6396 21.2917 32.0833 17.5 32.0833C13.7083 32.0833 10.2667 30.6396 7.67084 28.2625C7.81667 26.8917 8.69167 25.55 10.2521 24.5C14.2479 21.8458 20.7813 21.8458 24.7479 24.5C26.3083 25.55 27.1833 26.8917 27.3292 28.2625Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M17.5 32.0833C25.5541 32.0833 32.0833 25.5541 32.0833 17.5C32.0833 9.44584 25.5541 2.91666 17.5 2.91666C9.44584 2.91666 2.91666 9.44584 2.91666 17.5C2.91666 25.5541 9.44584 32.0833 17.5 32.0833Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>
    <svg v-else-if="icon == 'copy'" width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M17 13.4V16.4C17 20.4 15.4 22 11.4 22H7.6C3.6 22 2 20.4 2 16.4V12.6C2 8.6 3.6 7 7.6 7H10.6" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M17 13.4H13.8C11.4 13.4 10.6 12.6 10.6 10.2V7L17 13.4Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M11.6 2H15.6" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M7 5C7 3.34 8.34 2 10 2H12.62" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M21.9999 8V14.19C21.9999 15.74 20.7399 17 19.1899 17" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M22 8H19C16.75 8 16 7.25 16 5V2L22 8Z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>
    <svg v-else-if="icon == 'again'" width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M14.55 21.67C18.84 20.54 22 16.64 22 12C22 6.48 17.56 2 12 2C5.33 2 2 7.56 2 7.56M2 7.56V3M2 7.56H4.01H6.44" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M2 12C2 17.52 6.48 22 12 22" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" stroke-dasharray="3 3"/>
    </svg>
    <svg v-else-if="icon == 'arrow-right'" width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M12 22C17.5228 22 22 17.5228 22 12C22 6.47715 17.5228 2 12 2C6.47715 2 2 6.47715 2 12C2 17.5228 6.47715 22 12 22Z" stroke="currentColor" stroke-width="2" stroke-miterlimit="10" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M10.74 15.53L14.26 12L10.74 8.46997" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>
    <svg v-else-if="icon == 'background'" xmlns="http://www.w3.org/2000/svg" width="343" height="242" viewBox="0 0 343 242" fill="none"><g filter="url(#filter0_d_3_45)"><g filter="url(#filter1_d_3_45)"><path d="M46.1777 123.962C6.29531 92.1573 5 0 5 0H343V160.421C343 160.421 292.719 234.403 245.203 232.911C195.198 231.342 195.846 168.113 150.838 146.266C113.242 128.018 78.8507 150.017 46.1777 123.962Z" fill="#161D6F"/></g><g filter="url(#filter2_d_3_45)"><path d="M71.4848 99.9416C39.9935 73.843 40.1726 0 40.1726 0H343V123.533C343 123.533 296.269 204.777 246.49 199.025C199.809 193.632 210.995 136.591 169.282 114.954C134.982 97.1628 101.235 124.598 71.4848 99.9416Z" fill="url(#paint0_linear_3_45)"/></g></g><defs><filter id="filter0_d_3_45" x="4.14213" y="-7.72081" width="346.579" height="248.579" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB"><feFlood flood-opacity="0" result="BackgroundImageFix"/><feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0" result="hardAlpha"/><feOffset dx="3.43147" dy="-3.43147"/><feGaussianBlur stdDeviation="2.14467"/><feComposite in2="hardAlpha" operator="out"/><feColorMatrix type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.25 0"/><feBlend mode="normal" in2="BackgroundImageFix" result="effect1_dropShadow_3_45"/><feBlend mode="normal" in="SourceGraphic" in2="effect1_dropShadow_3_45" result="shape"/></filter><filter id="filter1_d_3_45" x="0.71066" y="0" width="346.579" height="241.512" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB"><feFlood flood-opacity="0" result="BackgroundImageFix"/><feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0" result="hardAlpha"/><feOffset dy="4.28934"/><feGaussianBlur stdDeviation="2.14467"/><feComposite in2="hardAlpha" operator="out"/><feColorMatrix type="matrix" values="0 0 0 0 0.12549 0 0 0 0 0.12549 0 0 0 0 0.12549 0 0 0 0.25 0"/><feBlend mode="normal" in2="BackgroundImageFix" result="effect1_dropShadow_3_45"/><feBlend mode="normal" in="SourceGraphic" in2="effect1_dropShadow_3_45" result="shape"/></filter><filter id="filter2_d_3_45" x="35.8833" y="0" width="311.406" height="207.896" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB"><feFlood flood-opacity="0" result="BackgroundImageFix"/><feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0" result="hardAlpha"/><feOffset dy="4.28934"/><feGaussianBlur stdDeviation="2.14467"/><feComposite in2="hardAlpha" operator="out"/><feColorMatrix type="matrix" values="0 0 0 0 0.12549 0 0 0 0 0.12549 0 0 0 0 0.12549 0 0 0 0.25 0"/><feBlend mode="normal" in2="BackgroundImageFix" result="effect1_dropShadow_3_45"/><feBlend mode="normal" in="SourceGraphic" in2="effect1_dropShadow_3_45" result="shape"/></filter><linearGradient id="paint0_linear_3_45" x1="343" y1="-1.84902e-06" x2="40.1726" y2="199.025" gradientUnits="userSpaceOnUse"><stop stop-color="#F5FDFF"/><stop offset="1" stop-color="#98DED9"/></linearGradient></defs></svg>
    <svg v-else-if="icon == 'share'" width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M16.96 6.17004C18.96 7.56004 20.34 9.77004 20.62 12.32" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M3.48999 12.37C3.74999 9.82997 5.10999 7.61997 7.08999 6.21997" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M8.19 20.9399C9.35 21.5299 10.67 21.8599 12.06 21.8599C13.4 21.8599 14.66 21.5599 15.79 21.0099" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M12.06 7.70001C13.5954 7.70001 14.84 6.45537 14.84 4.92001C14.84 3.38466 13.5954 2.14001 12.06 2.14001C10.5247 2.14001 9.28003 3.38466 9.28003 4.92001C9.28003 6.45537 10.5247 7.70001 12.06 7.70001Z" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M4.82999 19.92C6.36534 19.92 7.60999 18.6753 7.60999 17.14C7.60999 15.6046 6.36534 14.36 4.82999 14.36C3.29464 14.36 2.04999 15.6046 2.04999 17.14C2.04999 18.6753 3.29464 19.92 4.82999 19.92Z" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M19.17 19.92C20.7054 19.92 21.95 18.6753 21.95 17.14C21.95 15.6046 20.7054 14.36 19.17 14.36C17.6347 14.36 16.39 15.6046 16.39 17.14C16.39 18.6753 17.6347 19.92 19.17 19.92Z" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>
    <svg v-else-if="icon == 'danger'" width="75" height="75" viewBox="0 0 75 75" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M37.4829 53.125H37.511" stroke="#FF5454" stroke-width="4" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M37.5 28.125V43.75" stroke="#FF5454" stroke-width="4" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M37.5 66.9062H18.5625C7.71872 66.9062 3.18747 59.1562 8.43747 49.6875L18.1875 32.125L27.375 15.625C32.9375 5.59375 42.0625 5.59375 47.625 15.625L56.8125 32.1563L66.5625 49.7188C71.8125 59.1875 67.25 66.9375 56.4375 66.9375H37.5V66.9062Z" stroke="#FF5454" stroke-width="4" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>



    <svg v-else xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none">
        <path d="M14 16.16L10.04 12.2" stroke="#FF6262" stroke-width="2" stroke-miterlimit="10" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M13.96 12.24L10 16.2" stroke="#FF6262" stroke-width="2" stroke-miterlimit="10" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M10 6H14C16 6 16 5 16 4C16 2 15 2 14 2H10C9 2 8 2 8 4C8 6 9 6 10 6Z" stroke="#FF6262" stroke-width="2" stroke-miterlimit="10" stroke-linecap="round" stroke-linejoin="round"/>
        <path d="M16 4.02002C19.33 4.20002 21 5.43002 21 10V16C21 20 20 22 15 22H9C4 22 3 20 3 16V10C3 5.44002 4.67 4.20002 8 4.02002" stroke="#FF6262" stroke-width="2" stroke-miterlimit="10" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>
</template>

<script>
export default {
    props: ["icon", "class"],
}
</script>

<style></style>
