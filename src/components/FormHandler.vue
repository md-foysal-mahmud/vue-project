<script>
export default {
  name: "FormHandler",
  data() {
    return {
     formValues: {
      name: '',
      profileSummary: '',
      country: '',
      jobLocation: [],
      remoteWork: 'no',
      skillSet: [],
      yearsOfExperience: '',
      age: null,
     }
    }
  },
  methods: {
    submitForm(event) {
      // event.preventDefault();    // <form @submit.prevent="submitForm">
      console.log('form values', this.formValues)
    },
  }
}
</script>

<template>
  <div>
    <pre>
      {{ JSON.stringify(formValues, null, 2) }}
    </pre>
  </div>
  <form @submit.prevent="submitForm">
    <!-- Text -->
    <div>
      <label for="name">Name</label>
      <input type="text" id="name" v-model.trim.lazy="formValues.name">
    </div>

    <!-- Textarea -->
    <div>
      <label for="profile">Profile Summary</label>
      <textarea id="profile" v-model="formValues.profileSummary" />
    </div>

    <!-- Single Select -->
    <div>
      <label for="country">Country</label>
      <select id="country" v-model="formValues.country">
        <option value="">Select a country</option>
        <option value="india">India</option>
        <option value="vietnam">Vietnam</option>
        <option value="singapore">Singapore</option>
      </select>
    </div>

    <!-- Multiple Select -->
    <div>
      <label for="job-location">Job location</label>
      <select id="job-location" v-model="formValues.jobLocation" multiple>
        <option value="india">India</option>
        <option value="vietnam">Vietnam</option>
        <option value="singapore">Singapore</option>
      </select>
    </div>

    <!-- Single Checkbox -->
    <div>
      <input
        id="remoteWork"
        type="checkbox"
        v-model="formValues.remoteWork"
        true-value="yes"
        false-value="no"
      />
      <label for="remoteWork"> Open to remote work?</label>
    </div>

    <!-- Multiple Checkbox -->
    <div>
      <label>Skill set</label>
      <input type="checkbox" id="html" value="html" v-model="formValues.skillSet" />
      <label for="html">HTML</label>
      <input type="checkbox" id="css" value="css" v-model="formValues.skillSet" />
      <label for="css">CSS</label>
      <input type="checkbox" id="javascript" value="javascript" v-model="formValues.skillSet" />
      <label for="javascript">JavaScript</label>
    </div>

    <!-- Radio Group -->
    <div>
      <label>Years of Experience</label>
      <input type="radio" id="0-2" value="0-2" v-model="formValues.yearsOfExperience" />
      <label for="0-2">0-2</label>
      <input type="radio" id="3-5" value="3-5" v-model="formValues.yearsOfExperience" />
      <label for="3-5">3-5</label>
      <input type="radio" id="6-10" value="6-10" v-model="formValues.yearsOfExperience" />
      <label for="6-10">5-10</label>
      <input type="radio" id="10+" value="10+" v-model="formValues.yearsOfExperience" />
      <label for="10+">10+</label>
    </div>
    <div>
      <label for="age">Age</label>
      <input type="number" id="age" v-model.number="formValues.age" />
    </div>
    <div>
      <button>Submit</button>
    </div>
  </form>
</template>

<style>
label {
  font-weight: bold;
  display: flex;
  margin-bottom: 5px;
}

input + label {
  font-weight: bold;
  display: inline-flex;
  margin-right: 20px;
}

input[type='text'],
textarea,
select {
  display: block;
  width: 400px;
  padding: 6px 12px;
  font-size: 14px;
  line-height: 1.42857143;
  color: #555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 4px;
}
</style>