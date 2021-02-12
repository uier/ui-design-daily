<template>
  <div>
    <header>
      <h1>UI Design Daily - Day 1273: Checkout UI Design</h1>
    </header>
    <main>
      <div id="card">
        <div id="card__title">Get unlimited access to everything</div>
        <div id="card__plan">
          <div
            class="card__plan__item"
            v-for="({ name, price, period }, index) in plans"
            :key="name"
            :class="{ 'card__plan__radio--active': checkedPlan.name === name }"
            @click="checkedPlan = plans[index]"
          >
            <div class="card__plan__header">
              <div class="card__plan__radio">
                <div class="card__plan__filled-radio" v-if="checkedPlan.name === name"></div>
              </div>
              <div style="margin-left: 14px">{{ name }}</div>
            </div>
            <div class="card__plan__body">{{ `$${price}/${period}` }}</div>
          </div>
        </div>
        <div id="card__payment__title">Total billed ${{ checkedPlan.price }}</div>
        <div id="card__payment__description">Enter your credit card details to complete subscription</div>
        <div id="card__form">
          <div id="card__credit-card-number">
            <div class="card__form__input">
              <label for="credit-card">Card number</label>
              <input type="text" name="credit-card" v-model="creditCardNumber" />
            </div>
          </div>
          <div id="card__credit-card-info">
            <div class="card__form__input">
              <label for="expiration-date">Expiration date</label>
              <input type="text" name="expiration-date" placeholder="MM/YY" />
            </div>
            <div class="card__form__input">
              <label for="security-code">Security code</label>
              <input type="text" name="security-code" value="123" />
            </div>
          </div>
        </div>
        <div id="card__note">By subscribing you agree to our Use of Service. Your payment method will be charged with ${{ checkedPlan.price }} and you’ll have access to all locked features until {{ expiredDate }}.</div>
        <button id="card__button" type="button">Pay Now</button>
      </div>
      <div id="card__shadow" />
    </main>
    <footer style="margin-bottom: 20px">
      <a target="_blank" rel="noopener noreferrer" href="https://www.uidesigndaily.com/posts/figma-checkout-day-1273">source of design</a>
      <a target="_blank" rel="noopener noreferrer" href="https://codepen.io/collection/DzQjZR" style="margin-left: 20px">source of code</a></footer>
  </div>
</template>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;700&display=swap");
#card__shadow {
  position: absolute;
  bottom: 0;
  background-color: #e8edff;
  width: 781px;
  height: 1007px;
}
#card__button {
  margin-top: 27px;
  padding: 45px 0;
  background-color: #5f82ff;
  border: 0;
  border-radius: 5px;
  color: white;
  font-size: 18px;
  font-weight: bold;
}
#card__note {
  margin-top: 50px;
  width: 533px;
  align-self: center;
  text-align: center;
  font-size: 14px;
  line-height: 24px;
}
#card__credit-card-info {
  display: flex;
  margin-top: 20px;
}
.card__form__input {
  flex: 1;
  display: flex;
  flex-direction: column;
  label {
    font-size: 14px;
    font-weight: bold;
  }
  input {
    margin-top: 5px;
    padding: 26px 0 26px 25px;
    font-size: 16px;
    border: 1px solid #ced5ec;
    border-radius: 5px;
    &:focus {
      outline: none;
      border: 1px solid #5f82ff;
    }
  }
  &:not(:first-child) {
    margin-left: 15px;
  }
}
#card__form {
  margin-top: 40px;
  display: flex;
  flex-direction: column;
}
#card__payment__description {
  margin-top: 10px;
  font-size: 16px;
}
#card__payment__title {
  margin-top: 60px;
  font-size: 22px;
  font-weight: bold;
}
.card__plan__radio--active {
  border: 1px solid #5f82ff !important;
  box-shadow: 0px 24px 24px -15px rgba(95, 130, 255, 0.15);
}
.card__plan__radio {
  height: 30px;
  width: 30px;
  margin: 0;
  position: relative;
  border: 1px solid #ced5ec;
  border-radius: 50%;
}
.card__plan__filled-radio {
  width: 18px;
  height: 18px;
  position: absolute;
  top: calc(50% - 9px);
  left: calc(50% - 9px);
  background: #5f82ff;
  border-radius: 50%;
}
.card__plan__body {
  margin-top: 1px;
  margin-left: 64px;
  font-size: 16px;
}
.card__plan__header {
  margin-top: 27px;
  margin-left: 20px;
  font-size: 18px;
  font-weight: bold;
  display: flex;
  align-items: center;
}
.card__plan__item {
  height: 104px;
  flex: 1;
  border: 1px solid #ced5ec;
  border-radius: 5px;
  &:not(:first-child) {
    margin-left: 15px;
  }
}
#card__plan {
  align-self: center;
  margin-top: 49px;
  width: 100%;
  display: flex;
}
#card__title {
  width: 256px;
  align-self: center;
  text-align: center;
  font-size: 24px;
  line-height: 32px;
  font-weight: bold;
}
#card {
  z-index: 10;
  background-color: #fff;
  padding: 80px 49px;
  display: flex;
  flex-direction: column;
  font-family: "Open Sans";
}
main {
  position: relative;
  background-color: #f4f6fd;
  height: 1200px;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
header,
footer {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 40px;
}
body {
  margin: 0;
}
</style>

<script>
const plans = [
  {
    name: "Monthly",
    price: 7,
    period: "month",
    label: null
  },
  {
    name: "Yearly",
    price: 50,
    period: "year",
    label: "Save $10"
  }
];
module.exports = {
  computed: {
    expiredDate() {
      let date = new Date();
      const period = this.checkedPlan.period === "month" ? 30 : 365;
      date.setDate(date.getDate() + period);
      const d = date.getDate();
      const m = date.toLocaleString("en-us", { month: "short" });
      const y = date.getFullYear();
      return d + " " + m + " " + y;
    },
    originalCardNumber() {
      const numberWithoutSpace = this.creditCardNumber.replace(/\s/g, "");
      return numberWithoutSpace;
    }
  },
  watch: {
    originalCardNumber() {
      const numberWithValidLength = this.originalCardNumber.slice(0, 16);
      const chunkedNumber = numberWithValidLength.match(/.{1,4}/g).join(" ");
      this.creditCardNumber = chunkedNumber;
    }
  },
  data: () => ({
    checkedPlan: plans[1],
    creditCardNumber: "1234 2234",
    plans
  })
};
</script>
