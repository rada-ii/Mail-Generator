<template>
  <div
    class="signature-preview"
    :style="
      templateType === 'template1'
        ? 'display: flex; flex-direction: row; align-items: center'
        : 'display: flex; flex-direction: column; align-items: center; justify-content: center; width: 100%; '
    "
  >
    <img
      v-if="companyLogo"
      :src="companyLogo"
      alt="Company Logo"
      class="img"
      :style="
        templateType === 'template1'
          ? 'width: 12.5rem; height: auto; margin-right: 0.5rem; padding-left: 0; padding-right: 0.5rem; border-right: 2px solid #ff0000;'
          : 'width: 12rem; height: auto; margin-bottom: 1rem;'
      "
    />
    <div
      :style="
        templateType === 'template1' ? '' : 'width: 100%; text-align: center;'
      "
    >
      <div
        id="nameJobContainer"
        :style="
          templateType === 'template1'
            ? 'display: flex; flex-direction: row; align-items: flex-start'
            : 'display: flex; flex-direction: column; align-items: center; text-align: center; margin-bottom: 0.5rem;'
        "
      >
        <div
          :style="
            templateType === 'template1'
              ? 'font-weight: 500; font-size: 1.125rem; line-height: 1rem; margin-right: 1rem; padding-right: 1rem; border-right: 2px solid #d1d5db; text-transform: capitalize;'
              : 'font-weight: 500; font-size: 1.25rem; line-height:1rem;'
          "
        >
          {{ name }}
        </div>
        <div
          :style="
            templateType === 'template1'
              ? 'font-weight: 400; font-size: 1.125rem; line-height: 1rem'
              : 'font-weight: 700; font-size: 1.25rem; line-height: 1.5rem; color:red;'
          "
        >
          {{ jobTitle }}
        </div>
      </div>
      <div
        class="data-user"
        :style="
          templateType === 'template1' ? '' : 'text-align: center; width: 100%;'
        "
      >
        <div
          v-if="phone"
          class="phone"
          :style="
            templateType === 'template1'
              ? 'font-weight: 300; font-size: 1.125rem; line-height: 1rem; color: #000; padding-top:0.5rem;'
              : 'font-weight: 300; font-size: 1.125rem; line-height: 1rem; color: #000;'
          "
        >
          <span style="font-weight: 300">phone:</span>
          {{ phone }}
        </div>
        <div
          v-if="email"
          class="email"
          :style="
            templateType === 'template1'
              ? 'font-weight: 300; font-size: 1.125rem; line-height: 1.6rem;'
              : 'font-weight: 300; font-size: 1.125rem; line-height: 1.6rem;'
          "
        >
          <span>email:&nbsp;</span>
          <a
            :href="`mailto:${email}`"
            style="color: #2563eb; text-decoration: underline"
          >
            {{ email }}
          </a>
        </div>
        <div
          v-if="website"
          class="site"
          :style="
            templateType === 'template1'
              ? 'font-weight: 300; font-size: 1.125rem; line-height: 0.7rem;'
              : 'font-weight: 300; font-size: 1.125rem; line-height: 0.7rem;'
          "
        >
          <span>website:&nbsp;</span>
          <a
            :href="`https://${website}`"
            target="_blank"
            style="color: #2563eb; text-decoration: underline"
          >
            {{ website }}
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    name: String,
    jobTitle: String,
    phone: String,
    email: String,
    website: String,
    companyLogo: String,
    templateType: String,
  },
};
</script>
