<template>
  <ul class="number-cards">
    <li class="number-card">
      <h3 class="number-card__text">حجوزات جديدة</h3>
      <span class="number-card__badge">20</span>
    </li>
  </ul>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.number-cards {
  list-style-type: none;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1rem;
  padding: 0;

  .number-card {
    border: 1px solid #ff94a6;
    border-radius: 2rem;
    display: flex;
    justify-content: space-around;
    align-items: center;
    padding-block: 1rem;
    cursor: pointer;
    box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.1);
    transition: all 0.3s ease-in-out;

    &:hover {
      box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.2);
    }

    .number-card__text {
      font-size: 1.5rem;
      font-weight: bold;
    }

    .number-card__badge {
      background-color: #ff94a6;
      color: #fff;
      border-radius: 1rem;
      padding: 1rem;
      font-size: 1.5rem;
      font-weight: bold;
    }
  }
}
</style>
