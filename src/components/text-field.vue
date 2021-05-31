<template>
  <div class="form_group field">
    <input
      @keydown="invalidRemove($event)"
      type="number"
      class="form_field"
      :placeholder="placeHolder"
      :name="placeHolder"
      :id="placeHolder"
      :value="value"
      @input="updateValue($event.target.value)"
    />
    <label for="name" class="form_label">{{ placeHolder }}</label>
  </div>
</template>





<script>
export default {
  name: "textField",
  props: {
    placeHolder: String,
    value: Number,
  },
  data() {
    return {
      invalid: ["e", "+", "-"],
    };
  },
  methods: {
    invalidRemove($event) {
      this.invalid.forEach((i) => {
        if ($event.key == i) {
          $event.preventDefault();
        }
      });
    },
    updateValue(v) {
      this.$emit("input", v);
    },
  },
};
</script>






<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Manrope");

$primary: #786fa6;
$secondary: #574b90;
$txt-color: #636e72;
$unfocused-color: #e66767;
.form_group {
  position: relative;
  padding: 15px 0 0;
  margin-top: 10px;
  width: 29.28vw;
  user-select: none;

  @media screen and (max-width: 1050px) {
    width: 35vw;
  }
  @media screen and (max-width: 750px) {
    width: 45vw;
  }
  @media screen and (max-width: 570px) {
    width: 60vw;
  }
  @media screen and (max-width: 480px) {
    width: 67vw;
  }
  @media screen and (max-width: 275px) {
    width: 62vw;
  }
}

.form_field {
  font-family: "Manrope", sans-serif;
  width: 100%;
  border: 0;
  border-bottom: 2px solid $unfocused-color;
  outline: 0;
  font-size: 1.3rem;
  color: $txt-color;
  padding: 7px 0;
  background: none;
  transition: 0.2s;

   @media screen and (max-width: 275px) {
    font-size: 1.1rem;
  }

  &::placeholder {
    color: transparent;
  }

  &:placeholder-shown ~ .form_label {
    font-size: 1.3rem;
    cursor: text;
    top: 20px;

   @media screen and (max-width: 275px) {
    font-size: 1.1rem;
  }

  }
}

.form_label {
  position: absolute;
  top: 0;
  display: block;
  transition: 0.2s;
  font-size: 1rem;
  color: $unfocused-color;

}

.form_field:focus {
  ~ .form_label {
    position: absolute;
    top: 0;
    display: block;
    transition: 0.2s;
    font-size: 1rem;
    color: $primary;
    font-weight: 700;
  }
  padding-bottom: 6px;
  font-weight: 700;
  border-width: 3px;
  border-color: $secondary;
  border-image-slice: 1;
}
.form_field {
  &:required,
  &:invalid {
    box-shadow: none;
  }
}

.form_field::-webkit-outer-spin-button,
.form_field::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

.form_field[type="number"] {
  -moz-appearance: textfield;
}
body {
  font-family: "Manrope", sans-serif;
}
</style>