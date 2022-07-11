<template>
  <Ul class="state-cards">
    <Li class="state-card state-card--green">
      <h3 class="state-card__number">530</h3>
      <div class="state-card__info text-green">
        <p class="state-card__text">حجوزات منتهية وقتها</p>
        <h6 class="state-card__rate">65%</h6>
      </div>
    </Li>
    <Li class="state-card state-card--yellow">
      <h3 class="state-card__number">166</h3>
      <div class="state-card__info text-yellow">
        <p class="state-card__text">حجوزات قريب وقتها</p>
        <h6 class="state-card__rate">15%</h6>
      </div>
    </Li>
    <Li class="state-card state-card--red">
      <h3 class="state-card__number">98</h3>
      <div class="state-card__info text-red">
        <p class="state-card__text">حجوزات لم ينتهي وقتها</p>
        <h6 class="state-card__rate">9%</h6>
      </div>
    </Li>
    <Li class="state-card state-card--blue">
      <h3 class="state-card__number">112</h3>
      <div class="state-card__info text-blue">
        <p class="state-card__text">
          حــــجـــوزات<br />
          مـــنـــازل
        </p>
        <h6 class="state-card__rate">11%</h6>
      </div>
    </Li>
  </Ul>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.state-cards {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  gap: 1rem;
  margin: 1rem 0;
  width: 50%;
  height: 25rem;
  list-style-type: none;
  padding: 0;

  .state-card {
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 1rem;
    border-radius: 0.5rem;
    background-color: #fff;
    box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.1);
    margin: 0.5rem 0;
    transition: all 0.3s ease-in-out;
    cursor: pointer;

    &:hover {
      box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.2);
    }

    &--green {
      background-color: rgba(204, 246, 208, 100);
    }

    &--yellow {
      background-color: rgba(254, 239, 198);
    }

    &--red {
      background-color: rgba(255, 202, 194, 100);
    }

    &--blue {
      background-color: rgba(209, 218, 249, 100);
    }

    &__number {
      color: #000;
      font-size: 3rem;
      font-weight: bold;
      padding-top: 2rem;
      flex: 1;
    }

    &__info {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }

    &__text {
      font-size: 1.5rem;
      font-weight: bold;
      padding: 0.5rem 2rem;
      text-align: center;

      &::after {
        content: "";
        display: block;
        width: 50%;
        margin: 0 auto;
        border: 1px solid;
      }
    }

    &__rate {
      font-size: 2rem;
      font-weight: bold;
    }
  }
}

.text-green {
  color: #2cc701;
}

.text-yellow {
  color: #e5a039;
}

.text-red {
  color: #ff2300;
}

.text-blue {
  color: #4169e2;
}
</style>
