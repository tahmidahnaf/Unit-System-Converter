<template>
  <button><slot></slot></button>
</template>




<script>
export default {
  name: "btn",
};
</script>





<style lang="scss" scoped>
button {
  display: inline-block;
  font-weight: 400;
  line-height: 2;
  color: #212529;
  text-align: center;
  text-decoration: none;
  vertical-align: middle;
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  border: none;
  padding: 0.375rem 0.75rem;
  -webkit-transition: all 0.3s ease-in-out;
  transition: all 0.3s ease-in-out;
  font-size: 17px;
  border-radius: 5px;
  background-image: -webkit-gradient(
    linear,
    left top,
    right bottom,
    from(#e74c3c),
    to(#e67e22)
  );
  background-image: linear-gradient(to bottom right, #e74c3c, #e67e22);
  @media screen and (max-width: 275px) {
    font-size: 13px;
  }
}
button:hover {
  -webkit-transform: translateY(-0.25em);
  transform: translateY(-0.25em);
  -webkit-box-shadow: 0 0.5em 0.5em -0.4em #ee5253;
  box-shadow: 0 0.5em 0.5em -0.4em #ee5253;
}
button:focus {
  outline: none;
  border: none;
}
</style>