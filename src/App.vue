<script setup>
import IdCard from "./components/IdCard.vue";
import Random from "./components/Random.vue";
import BoxColor from "./components/BoxColor.vue";
import CreditCard from "./components/CreditCard.vue";
import Rating from "./components/Rating.vue";
import DriverCard from "./components/DriverCard.vue";
</script>

<template>
  <h1>Creación de componentes con Vue</h1>
  <p>Crea a continuación todos los componentes del ejercicio.</p>

  <!-- Iteration 1 -->
  <IdCard
    last-name="Doe"
    first-name="John"
    gender="male"
    :height="178"
    :birth="new Date('1992-07-14')"
    picture="https://randomuser.me/api/portraits/men/44.jpg"
  />

  <IdCard
    last-name="Delores"
    first-name="Obrien"
    gender="female"
    :height="172"
    :birth="new Date('1988-05-11')"
    picture="https://randomuser.me/api/portraits/women/44.jpg"
  />

  <!-- Iteration 2 -->
  <Random :min="1" :max="6" />
  <Random :min="1" :max="100" />

  <!-- Iteration 3 -->
  <BoxColor :r="255" :g="0" :b="0" />
  <BoxColor :r="128" :g="255" :b="0" />

  <!-- Iteration 4 -->
  <CreditCard
    type="Visa"
    number="0123456789018845"
    :expiration-month="3"
    :expiration-year="2021"
    bank="BNP"
    owner="Maxence Bouret"
    bg-color="#11aa99"
    color="white"
  />

  <CreditCard
    type="Master Card"
    number="0123456789010995"
    :expiration-month="3"
    :expiration-year="2021"
    bank="N26"
    owner="Maxence Bouret"
    bg-color="#eeeeee"
    color="#222222"
  />

  <CreditCard
    type="Visa"
    number="0123456789016984"
    :expiration-month="12"
    :expiration-year="2019"
    bank="Name of the Bank"
    owner="Firstname Lastname"
    bg-color="#ddbb55"
    color="white"
  />

  <!-- Iteration 5 -->
  <Rating :rate="0" />
  <Rating :rate="1.49" />
  <Rating :rate="1.5" />
  <Rating :rate="3" />
  <Rating :rate="4" />
  <Rating :rate="5" />

  <!-- Iteration 6 -->
  <DriverCard
    name="Travis Kalanick"
    :rating="4.2"
    img="https://si.wsj.net/public/resources/images/BN-TY647_37gql_OR_20170621052140.jpg?width=620&height=428"
    :car="{ model: 'Toyota Corolla Altis', licensePlate: 'CO42DE' }"
  />

  <DriverCard
    name="Dara Khosrowshahi"
    :rating="4.9"
    img="https://ubernewsroomapi.10upcdn.com/wp-content/uploads/2017/09/Dara_ELT_Newsroom_1000px.jpg"
    :car="{ model: 'Audi A3', licensePlate: 'BE33ER' }"
  />

  <LikeButton />

  <ClickablePicture
    img="/img/maxence.png"
    img-clicked="/img/maxence-glasses.png"
  />

  <Dice />

  <Carousel
    :images="[
      'https://randomuser.me/api/portraits/women/1.jpg',
      'https://randomuser.me/api/portraits/men/1.jpg',
      'https://randomuser.me/api/portraits/women/2.jpg',
      'https://randomuser.me/api/portraits/men/2.jpg'
    ]"
  />

  <NumbersTable :limit="12" />

  <FaceBook />

  <SignupPage />

  <RGBColorPicker />

</template>
