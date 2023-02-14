<template>
  <div class="contact">
    <div class="row">
      <div class="col-md-6">
        <div
          :class="`contact-title ${
            $i18n.locale === 'ar' ? 'text-end' : 'text-start'
          }`"
        >
          {{ $t("contact.GetIn") }}<span>{{ $t("contact.Touch") }}</span>
        </div>
        <div
          :class="`contact-body contact-right ${
            $i18n.locale === 'ar' ? 'text-end' : 'text-start'
          }`"
        >
          <ul class="list-unstyled">
            <li class="list-item">
              <font-awesome-icon
                :class="`contact-icon ${
                  $i18n.locale === 'ar' ? 'ms-4' : 'me-4'
                }`"
                :icon="{ prefix: 'fas', iconName: 'map-marker-alt' }"
              />
              {{ $t("contact.Syria")
              }}<span>{{ $t("contact.Hama - Salamiyeh") }}</span>
            </li>
            <li class="list-item">
              <font-awesome-icon
                :class="`contact-icon ${
                  $i18n.locale === 'ar' ? 'ms-4' : 'me-4'
                }`"
                :icon="{ prefix: 'fas', iconName: 'envelope' }"
              />
              fadi6ka@<span>gmail.com</span>
            </li>
            <li class="list-item">
              <font-awesome-icon
                :class="`contact-icon ${
                  $i18n.locale === 'ar' ? 'ms-4' : 'me-4'
                }`"
                :icon="{ prefix: 'fas', iconName: 'phone' }"
              />
              &plus;963&nbsp;<span>938&nbsp;123&nbsp;636</span>
            </li>
            <li class="list-item">
              <font-awesome-icon
                :class="`contact-icon ${
                  $i18n.locale === 'ar' ? 'ms-4' : 'me-4'
                }`"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              {{ $t("contact.Freelance")
              }}<span>{{ $t("contact.Available") }}</span>
            </li>
          </ul>
        </div>
      </div>
      <div class="col-md-6">
        <div
          :class="`contact-title ${
            $i18n.locale === 'ar' ? 'text-end' : 'text-start'
          }`"
        >
          {{ $t("contact.Contact") }}<span>{{ $t("contact.Form") }}</span>
        </div>
        <div
          :class="`contact-body contact-right ${
            $i18n.locale === 'ar' ? 'text-end' : 'text-start'
          }`"
        >
          <form
            action="https://formspree.io/f/xwkyjdzo"
            method="POST"
            class="contact-form"
            v-on:submit="sendButton"
          >
            <div>
              <input
                class="contact-item"
                id="name"
                type="text"
                name="name"
                v-model="v$.form.name.$model"
                @blur="v$.form.name.$touch()"
                v-on:blur="inputBlur"
                v-on:click="inputClick"
              />
              <label for="name" class="contact-label contact-label-normal">{{
                $t("contact.Name")
              }}</label>
              <div
                class="input-errors"
                v-for="(error, index) of v$.form.name.$errors"
                :key="index"
              >
                <div class="error-msg">{{ error.$message }}</div>
              </div>
            </div>
            <div>
              <input
                class="contact-item"
                id="email"
                type="email"
                name="email"
                v-model="v$.form.email.$model"
                @blur="v$.form.email.$touch()"
                v-on:blur="inputBlur"
                v-on:click="inputClick"
              />
              <label for="email" class="contact-label contact-label-normal">{{
                $t("contact.Email")
              }}</label>
              <div
                class="input-errors"
                v-for="(error, index) of v$.form.email.$errors"
                :key="index"
              >
                <div class="error-msg">{{ error.$message }}</div>
              </div>
            </div>
            <div>
              <textarea
                class="contact-item text-area"
                id="textarea"
                name="message"
                v-model="v$.form.message.$model"
                @blur="v$.form.message.$touch()"
                v-on:blur="inputBlur"
                v-on:click="inputClick"
              ></textarea>
              <label
                for="textarea"
                class="contact-label contact-label-message"
                >{{ $t("contact.Message") }}</label
              >
              <div
                class="input-errors"
                v-for="(error, index) of v$.form.message.$errors"
                :key="index"
              >
                <div class="error-msg">{{ error.$message }}</div>
              </div>
            </div>
            <div class="row">
              <div class="col-12 col-md-12 col-lg-6">
                <div class="contact-btn submit buttons-width">
                  <button
                    class="submit-btn-item"
                    type="submit"
                    :disabled="v$.form.$invalid"
                  >
                    {{ $t("contact.Send Message") }}
                  </button>
                </div>
              </div>
              <div class="col-6 col-lg-6 col-xl-6 col-xxl-6">
                <div class="contact-btn clear">
                  <button
                    class="submit-btn-item"
                    type="reset"
                    v-on:click="clearButton"
                  >
                    {{ $t("contact.Clear") }}
                  </button>
                </div>
              </div>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import useVuelidate from "@vuelidate/core";
import { required, email, minLength } from "@vuelidate/validators";
import $ from "jquery";

export function validName(name) {
  let validNamePattern = new RegExp("^[a-zA-Z]+(?:[-'\\s][a-zA-Z]+)*$");
  if (validNamePattern.test(name)) {
    return true;
  }
  return false;
}

export default {
  setup() {
    return { v$: useVuelidate() };
  },
  data: function () {
    return {
      form: {
        name: "",
        email: "",
        message: "",
      },
    };
  },
  validations() {
    return {
      form: {
        name: {
          required,
          name_validation: {
            $validator: validName,
            $message:
              "Invalid Name. Valid name only contain letters, dashes (-) and spaces",
          },
        },
        email: { required, email },
        message: { required, min: minLength(20) },
      },
    };
  },
  methods: {
    inputClick(e) {
      $(e.target).siblings().addClass("active");
      $(e.target).addClass("active");
    },
    inputBlur(e) {
      if ($(e.target).val() == "") {
        $(e.target).siblings().removeClass("active");
        $(e.target).removeClass("active");
      }
    },
    sendButton() {
      this.name = "";
      this.email = "";
      this.message = "";
    },
    clearButton() {
      $(".contact-item").siblings().removeClass("active");
      $(".contact-item").css("border-bottom", "1px solid #fff");
    },
  },
  name: "ContactView",
};
</script>

<style lang="scss" scoped>
.contact {
  @media (max-width: 575px) {
    padding: 0 40px;
  }
  .contact-title {
    margin-top: 50px;
    font-size: 26px;
    font-weight: bold;
    letter-spacing: 1px;
  }
  .contact-body {
    padding: 20px 10px;
    .list-item {
      font-size: 18px;
      margin-bottom: 40px;
      .contact-icon {
        font-size: 35px;
      }
    }
    .contact-form {
      padding: 0;
      .contact-item {
        display: block;
        position: relative;
        border: none;
        // border-bottom: 1px solid #fff;
        background: transparent;
        margin-top: 40px;
        width: 100%;
        // color: #fff;
        outline: none;
        transition: 0.5s;
        z-index: 1;
        overflow: visible;
        // &.active {
        //   border-bottom: 1px solid rgb(215, 0, 0);
        // }
        &.text-area {
          min-height: 100px;
        }
      }
      .contact-label {
        position: absolute;
        // color: rgba(255, 255, 255, 0.432);
        // top: 0;
        transition: 0.5s;
        font-size: 20px;
        &.active {
          // color: rgb(215, 0, 0);
          font-size: 15px;
          &.contact-label-normal {
            transform: translate(1px, -45px);
          }
          &.contact-label-message {
            transform: translate(1px, -115px);
          }
        }
      }
      .contact-label-normal {
        transform: translate(10px, -30px);
      }
      .contact-label-message {
        transform: translate(10px, -100px);
      }
      .input-errors {
        font-size: 13px;
        margin-top: 5px;
      }
      .contact-item-btn {
        padding: 7px 20px;
        margin: 0 10px;
      }
      .contact-btn {
        position: relative;
        width: 175px;
        height: 50px;
        margin: 20px;
        .submit-btn-item {
          position: absolute;
          top: 0;
          left: 0;
          width: 100%;
          height: 100%;
          display: flex;
          justify-content: center;
          align-items: center;
          border-radius: 30px;
          z-index: 1;
          font-weight: 400;
          letter-spacing: 1px;
          overflow: hidden;
          transition: 0.3s;
          backdrop-filter: blur(15px);
          &::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 50%;
            height: 100%;
            transform: skewX(45deg) translateX(0);
            transition: 0.5s;
          }
        }
        &:hover {
          .submit-btn-item {
            letter-spacing: 3px;
            &::before {
              transform: skewX(45deg) translateX(200%);
            }
          }
          &::before {
            bottom: 0;
            height: 50%;
            width: 80%;
            border-radius: 30px;
            transition-delay: 0.3s;
          }
          &::after {
            top: 0;
            height: 50%;
            width: 80%;
            border-radius: 30px;
            transition-delay: 0.3s;
          }
        }
        &::before {
          content: "";
          position: absolute;
          left: 50%;
          transform: translateX(-50%);
          bottom: -5px;
          width: 30px;
          height: 10px;
          border-radius: 10px;
          transition: 0.3s;
          transition-delay: 0s;
        }
        &::after {
          content: "";
          position: absolute;
          left: 50%;
          transform: translateX(-50%);
          top: -5px;
          width: 30px;
          height: 10px;
          border-radius: 10px;
          transition: 0.3s;
          transition-delay: 0s;
        }
      }
    }
  }
}
</style>
