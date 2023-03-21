<template>
  <div class="card">
    <div class="card-img">
      <img :src="post.img" alt="" />
      <div class="card-text">
        <p>
          {{ post.text }}
        </p>
      </div>
    </div>
    <div class="card-title">
      <p>{{ post.title }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "MenuSlideCard",
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.card {
  max-width: 285px;
  box-shadow: 0px 0px 10px 1px rgba(97, 97, 97, 0.25);
  margin: 10px;

  @media screen and (max-width: 800px) {
    max-width: 200px;
  }
  &-img {
    width: 285px;
    height: 406px;
    position: relative;

    @media screen and (max-width: 800px) {
      width: 200px;
      height: 265px;
    }

    &:hover {
      .card-text {
        opacity: 1;
      }
    }
    img {
      width: 100%;
      height: 100%;
    }
  }

  &-title {
    height: 62px;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 0 10px;

    @media screen and (max-width: 800px) {
      height: 50px;
    }

    p {
      line-height: 110%;

      @media screen and (max-width: 800px) {
        font-size: 14px;
      }
    }
  }

  &-text {
    pointer-events: none;
    opacity: 0;
    position: absolute;
    top: 0;
    height: 406px;
    padding: 22px 24px 30px 23px;
    background: linear-gradient(
      0deg,
      rgba(93, 94, 95, 0.85),
      rgba(93, 94, 95, 0.85)
    );
    transition: 0.3s;

    @media screen and (max-width: 800px) {
      width: 200px;
      height: 265px;
      padding: 15px 17px 23px 16px;
    }
    p {
      color: #fff;
      font-weight: 500;
      line-height: 130%;

      @media screen and (max-width: 800px) {
        font-size: 12px;
      }
    }
  }
}
</style>