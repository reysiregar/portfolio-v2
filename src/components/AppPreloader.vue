<template>
  <div class="preloader">
    <div class="atom">
      <div class="electron"></div>
      <div class="electron"></div>
      <div class="electron"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AppPreloader',
};
</script>

<style scoped>
.preloader {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: #1e1e1e;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}
@keyframes atom {
  from { transform: none; }
  to { transform: translateY(-10px); }
}
@keyframes electron-circle1 {
  from { transform: rotateY(70deg) rotateZ(20deg); }
  to { transform: rotateY(70deg) rotateZ(380deg); }
}
@keyframes electron1 {
  from { transform: rotateZ(-20deg) rotateY(-70deg); }
  to { transform: rotateZ(-380deg) rotateY(-70deg); }
}
@keyframes electron-circle2 {
  from { transform: rotateY(60deg) rotateX(60deg) rotateZ(-30deg); }
  to { transform: rotateY(60deg) rotateX(60deg) rotateZ(330deg); }
}
@keyframes electron2 {
  from { transform: rotateZ(30deg) rotateX(-60deg) rotateY(-60deg); }
  to { transform: rotateZ(-330deg) rotateX(-60deg) rotateY(-60deg); }
}
@keyframes electron-circle3 {
  from { transform: rotateY(-60deg) rotateX(60deg) rotateZ(100deg); }
  to { transform: rotateY(-60deg) rotateX(60deg) rotateZ(460deg); }
}
@keyframes electron3 {
  from { transform: rotateZ(-100deg) rotateX(-60deg) rotateY(60deg); }
  to { transform: rotateZ(-460deg) rotateX(-60deg) rotateY(60deg); }
}
.atom {
  margin: 50px auto;
  width: 120px;
  height: 120px;
  position: relative;
  animation: atom 1s ease-in-out infinite alternate;
  perspective: 300px;
  transform-style: preserve-3d;
}
.atom:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  margin: auto;
  width: 20px;
  height: 20px;
  border-radius: 10px;
  background: #f3f4f6;
}
.atom .electron {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  margin: auto;
  width: 100px;
  height: 100px;
  border-radius: 50px;
  border: 2px solid #f3f4f6;
  transform-style: preserve-3d;
}
.atom .electron:before {
  content: '';
  position: absolute;
  top: -4px;
  left: 0;
  right: 0;
  margin: auto;
  width: 8px;
  height: 8px;
  border-radius: 4px;
  background: #fff;
  transform-origin: 50% 50% 0;
}
.atom .electron:nth-child(1) {
  transform: rotateY(70deg) rotateZ(20deg);
  animation: electron-circle1 3s linear infinite;
}
.atom .electron:nth-child(2) {
  transform: rotateY(60deg) rotateX(60deg) rotateZ(-30deg);
  animation: electron-circle2 3s linear infinite;
}
.atom .electron:nth-child(3) {
  transform: rotateY(-60deg) rotateX(60deg) rotateZ(100deg);
  animation: electron-circle3 3s linear infinite;
}
.atom .electron:nth-child(1):before {
  transform: rotateZ(-20deg) rotateY(-70deg);
  animation: electron1 3s linear infinite;
}
.atom .electron:nth-child(2):before {
  transform: rotateZ(30deg) rotateX(-60deg) rotateY(-60deg);
  animation: electron2 3s linear infinite;
}
.atom .electron:nth-child(3):before {
  transform: rotateZ(-100deg) rotateX(-60deg) rotateY(60deg);
  animation: electron3 3s linear infinite;
}
</style> 