<template>
  <div id="homeCarousel" class="carousel slide carousel-fade">
    <div class="carousel-inner">
      <div class="carousel-item active">
        <img src="../assets/img/horse-race.jpg" class="d-block w-100" alt="Horses in a race" />
      </div>
      <div class="carousel-item">
        <img src="../assets/img/horse-dressure.jpg" class="d-block w-100" alt="Horse being ridden for dressure" />
      </div>
      <div class="carousel-item">
        <img src="../assets/img/horse-jump.jpg" class="d-block w-100" alt="Horse in a jumping contest" />
      </div>
      <div class="carousel-item">
        <img src="../assets/img/horse-cowboy.jpg" class="d-block w-100" alt="Horse ridden cowboy style" />
      </div>
    </div>
    <button class="carousel-control-prev" type="button" data-bs-target="#homeCarousel" data-bs-slide="prev">
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Previous</span>
    </button>
    <button class="carousel-control-next" type="button" data-bs-target="#homeCarousel" data-bs-slide="next">
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Next</span>
    </button>
  </div>
</template>

<style scoped>
#homeCarousel {
  width: 100%;
}
</style>
