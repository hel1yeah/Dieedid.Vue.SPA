<template>
  <footer class="footer">
    <div class="container">
      <div class="wrapper__position">
        <ul class="info">
          <li class="info__item">Контакты</li>
          <li class="info__item">Часто задаваемые вопросы</li>
          <li class="info__item">Правила и условия</li>
          <li class="info__item">
            <div class="social">
              <div class="social__item">
                <svg class="header__logo-facebook">
                  <use
                    xlink:href="../../assets/images/sprite/sprite.svg#logo-facebook"
                  ></use>
                </svg>
              </div>
              <div class="social__item">
                <svg class="header__logo-instagram">
                  <use
                    xlink:href="../../assets/images/sprite/sprite.svg#logo-instagram"
                  ></use>
                </svg>
              </div>
              <div class="social__item">
                <svg class="header__logo-youtube">
                  <use
                    xlink:href="../../assets/images/sprite/sprite.svg#logo-youtube"
                  ></use>
                </svg>
              </div>
            </div>
          </li>
        </ul>
        <div class="copyright">
          © 2020. Все права защищены. Копирование материала с этого сайта
          возможно только с разрешения правообладателя и с размещением ссылки на
          первоисточник.
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer"
};
</script>

<style lang="scss">
footer {
  background-color: rgba(2, 18, 11, 0.6);
  flex-shrink: 0;
}
.wrapper__position {
  display: flex;
  align-items: center;
  flex-direction: column;
}
.info {
  font: {
    family: "Roboto", sans-serif;
    size: 0.7778rem;
    style: normal;
    weight: normal;
  }
  color: $gold;
  text-decoration-line: underline;
  width: 100%;
  padding: 0 100px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 30px 100px 20px;

  &__item {
    display: block;
    text-decoration: none;
    cursor: pointer;
  }
  &__item svg {
    cursor: pointer;
    width: 27px;
    height: 27px;
  }
}
.social {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.copyright {
  color: $white;
  font-weight: 300;
  font-size: 12px;
  padding: 7px 0 14px;
  text-align: center;
}
</style>
