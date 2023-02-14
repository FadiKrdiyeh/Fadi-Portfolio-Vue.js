<template>
  <div class="resume">
    <div class="row">
      <div class="col-md-6 col-sm-12">
        <div class="left education-experience">
          <h3
            :class="`education-experience-title ${
              $i18n.locale === 'ar' ? 'text-end me-4' : 'text-start ms-4'
            }`"
          >
            {{ $t("resume.Experience") }}
          </h3>
          <div class="education-experience-body experience-body">
            <div class="lifetime">
              <div class="lifetime-item">
                <div class="circle"></div>
                <div class="row">
                  <div class="col-4">
                    <div
                      :class="`lifetime-date ${
                        $i18n.locale === 'ar' ? 'pe-5' : 'ps-5'
                      }`"
                    >
                      <div class="start">2020</div>
                      <div class="end">{{ $t("resume.present") }}</div>
                    </div>
                  </div>
                  <div class="col-8">
                    <div
                      :class="`lifetime-description ${
                        $i18n.locale === 'ar'
                          ? 'text-end pe-2'
                          : 'text-start ps-2'
                      }`"
                    >
                      <h4>{{ $t("resume.Full Stack Developer") }}</h4>
                      <div class="progress">
                        <div
                          class="progress-bar bg-custom-red"
                          role="progressbar"
                          style="width: 85%"
                          aria-valuenow="75"
                          aria-valuemin="0"
                          aria-valuemax="100"
                        ></div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
              <div class="lifetime-item">
                <div class="circle"></div>
                <div class="row">
                  <div class="col-4">
                    <div
                      :class="`lifetime-date ${
                        $i18n.locale === 'ar' ? 'pe-5' : 'ps-5'
                      }`"
                    >
                      <div class="start">2019</div>
                      <div class="end">{{ $t("resume.present") }}</div>
                    </div>
                  </div>
                  <div class="col-8">
                    <div
                      :class="`lifetime-description ${
                        $i18n.locale === 'ar'
                          ? 'text-end pe-2'
                          : 'text-start ps-2'
                      }`"
                    >
                      <h4>{{ $t("resume.Front End Developer") }}</h4>
                      <div class="progress">
                        <div
                          class="progress-bar bg-custom-red"
                          role="progressbar"
                          style="width: 100%"
                          aria-valuenow="75"
                          aria-valuemin="0"
                          aria-valuemax="100"
                        ></div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
              <div class="lifetime-item">
                <div class="circle"></div>
                <div class="row">
                  <div class="col-4">
                    <div
                      :class="`lifetime-date ${
                        $i18n.locale === 'ar' ? 'pe-5' : 'ps-5'
                      }`"
                    >
                      <div class="start">2020</div>
                      <div class="end">{{ $t("resume.present") }}</div>
                    </div>
                  </div>
                  <div class="col-8">
                    <div
                      :class="`lifetime-description ${
                        $i18n.locale === 'ar'
                          ? 'text-end pe-2'
                          : 'text-start ps-2'
                      }`"
                    >
                      <h4>{{ $t("resume.Back End Developer") }}</h4>
                      <div class="progress">
                        <div
                          class="progress-bar bg-custom-red"
                          role="progressbar"
                          style="width: 80%"
                          aria-valuenow="75"
                          aria-valuemin="0"
                          aria-valuemax="100"
                        ></div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="col-md-6 col-sm-12">
        <div class="right education-experience">
          <h3
            :class="`education-experience-title ${
              $i18n.locale === 'ar' ? 'text-end me-4' : 'text-start ms-4'
            }`"
          >
            {{ $t("resume.Education") }}
          </h3>
          <div class="education-experience-body education-body">
            <div class="lifetime">
              <div class="lifetime-item">
                <div class="circle"></div>
                <div class="row">
                  <div class="col-4">
                    <div
                      :class="`lifetime-date ${
                        $i18n.locale === 'ar' ? 'pe-5' : 'ps-5'
                      }`"
                    >
                      <div class="start">2021</div>
                      <div class="end">{{ $t("resume.present") }}</div>
                    </div>
                  </div>
                  <div class="col-8">
                    <div
                      :class="`lifetime-description ${
                        $i18n.locale === 'ar'
                          ? 'text-end pe-2'
                          : 'text-start ps-2'
                      }`"
                    >
                      <h4>{{ $t("resume.Applied College") }}</h4>
                      <small>{{
                        $t("resume.Computer Technology Sciences")
                      }}</small>
                    </div>
                  </div>
                </div>
              </div>
              <div class="lifetime-item">
                <div class="circle"></div>
                <div class="row">
                  <div class="col-4">
                    <div
                      :class="`lifetime-date ${
                        $i18n.locale === 'ar' ? 'pe-5' : 'ps-5'
                      }`"
                    >
                      <div class="start">2019</div>
                      <div class="end">2021</div>
                    </div>
                  </div>
                  <div class="col-8">
                    <div
                      :class="`lifetime-description ${
                        $i18n.locale === 'ar'
                          ? 'text-end pe-2'
                          : 'text-start ps-2'
                      }`"
                    >
                      <h4>{{ $t("resume.Computer Technical Institute") }}</h4>
                      <small>{{
                        $t("resume.Graduated From Computer Technical Institute")
                      }}</small>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="skills">
      <div class="row justify-content-center">
        <div class="skills-title">{{ $t("resume.My skills") }}</div>
        <div class="col-lg-4 col-md-6 unorder-list">
          <ul
            :class="`list-unstyled ${
              $i18n.locale === 'ar' ? 'text-end' : 'text-start'
            }`"
          >
            <li>
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              HTML
            </li>
            <li>
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              CSS
            </li>
            <li>
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              Sass
            </li>
            <li>
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              Javascript
            </li>
            <li>
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              jQuery
            </li>
            <li>
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              Vue
            </li>
          </ul>
        </div>
        <div class="col-lg-4 col-md-6 unorder-list">
          <ul
            :class="`list-unstyled ${
              $i18n.locale === 'ar' ? 'text-end' : 'text-start'
            }`"
          >
            <li>
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              Vuetify
            </li>
            <li>
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              PHP
            </li>
            <li>
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              Laravel / API
            </li>
            <li>
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              MySQL / Databases
            </li>
            <li>
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              Ajax
            </li>
            <li>
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              Bootstrap
            </li>
          </ul>
        </div>
        <div class="col-lg-4 col-md-6 unorder-list">
          <ul
            :class="`list-unstyled ${
              $i18n.locale === 'ar' ? 'text-end' : 'text-start'
            }`"
          >
            <li>
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              Fontawesome
            </li>
            <li>
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              Typescript
            </li>
            <li>
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              ES6
            </li>
            <li>
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              Git & Github
            </li>
            <li>
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              User interface design
            </li>
            <li>
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              Responsive websites / web applications
            </li>
          </ul>
        </div>
        <div class="skills-title">{{ $t("resume.Others:") }}</div>
        <div class="col-12 unorder-list">
          <ul
            :class="`list-unstyled ${
              $i18n.locale === 'ar' ? 'text-end' : 'text-start'
            }`"
          >
            <li class="other-item">
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              {{ $t("resume.Microsoft office") }}
            </li>
            <li class="other-item">
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              {{ $t("resume.The ability to learn anything quickly") }}
            </li>
            <li class="other-item">
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              {{ $t("resume.Remote working") }}
            </li>
            <li class="other-item">
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              {{ $t("resume.Im social and I accept advices and warnings") }}
            </li>
            <li class="other-item">
              <font-awesome-icon
                class="skill-icons"
                :icon="{ prefix: 'fas', iconName: 'check' }"
              />
              {{
                $t(
                  "resume.Soon I will probably learn other things like Wordpress React Angular ASPNet Photoshop etc"
                )
              }}
            </li>
          </ul>
        </div>
      </div>
    </div>
    <div class="download-cv-button">
      <div class="row">
        <div class="col-12">
          <a
            href="https://docs.google.com/document/d/1H1ZLC_DEHiBxDecSnr2rmvyaQfJv1J0oimP3WYSLnLU/edit?usp=sharing"
            target="_blank"
            class="btn-download"
            v-on:mousemove="mouseMove"
            ><span
              >{{ $t("resume.Download Resume")
              }}<font-awesome-icon
                :class="`download-icons ${
                  $i18n.locale === 'ar' ? 'me-2' : 'ms-2'
                }`"
                :icon="{ prefix: 'fas', iconName: 'file-download' }" /></span
          ></a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import $ from "jquery";

export default {
  methods: {
    mouseMove(e) {
      const x = e.pageX - $(".btn-download").offset().left;
      const y = e.pageY - $(".btn-download").offset().top;

      $(".btn-download").css({
        "--x": x + "px",
        "--y": y + "px",
      });
    },
  },
  name: "ResumeView",
};
</script>
<style lang="scss" scoped>
.resume {
  > .row {
    margin-top: 50px;
    .education-experience {
      .education-experience-title {
        font-weight: bold;
        font-size: 20px;
      }
      .education-experience-body {
        .lifetime {
          margin-top: 40px;
          padding-top: 55px;
          position: relative;
          padding-bottom: 1px;
          &::before {
            left: 30px;
            bottom: 0;
            content: "";
            height: 100%;
            position: absolute;
            top: 0;
            width: 2px;
          }
          .lifetime-item {
            position: relative;
            margin-bottom: 40px;
            .circle {
              position: absolute;
              width: 25px;
              height: 25px;
              border-radius: 50%;
              left: 18.5px;
            }
            .lifetime-date {
              text-transform: uppercase;
              text-align: center;
              font-size: 13px;
              font-weight: bold;
            }
            .lifetime-description {
              line-height: 0.5;
              h4 {
                font-size: 20px;
                letter-spacing: 0.5px;
              }
              small {
                font-size: 12px;
              }
            }
          }
        }
      }
    }
    .right {
      @media (max-width: 767px) {
        margin-top: 100px;
      }
      .lifetime {
        margin-top: 60px !important;
      }
    }
  }
  .skills {
    .skills-title {
      font-size: 50px;
      margin-top: 50px;
    }
    .unorder-list {
      display: flex;
      justify-content: space-around;
      @media (max-width: 575px) {
        justify-content: flex-start;
        padding-left: 100px;
      }
      ul {
        margin-top: 30px;
        li {
          font-size: 24px;
          .skill-icons {
            font-size: 25px;
            padding-right: 10px;
          }
        }
      }
      .other-item {
        @media (max-width: 575px) {
          margin-bottom: 25px;
        }
      }
    }
  }
  .download-cv-button {
    .btn-download {
      position: relative;
      display: inline-flex;
      justify-content: center;
      align-items: center;
      padding: 10px 30px;
      width: 250px;
      height: 70px;
      text-decoration: none;
      letter-spacing: 1px;
      overflow: hidden;
      margin-top: 50px;
      transition: text-shadow 0.5s;
      &::before {
        content: "";
        position: absolute;
        top: var(--y);
        left: var(--x);
        transform: translate(-50%, -50%);
        width: 0;
        height: 0;
        border-radius: 50%;
        transition: width 0.5s, height 0.5s;
      }
      &:hover {
        text-shadow: none;
        &::before {
          width: 500px;
          height: 500px;
        }
      }
      span {
        position: relative;
        z-index: 1;
        .download-icons {
          font-size: 24px;
        }
      }
    }
  }
}
</style>
