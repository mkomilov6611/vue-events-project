<template>
  <div>
    <input
      type="email"
      v-model="email"
      placeholder="What`s your email"
      @blur="$v.email.$touch()"
    />
    <div v-if="$v.email.$error">
      <p v-if="!$v.email.email">Please enter a valid email</p>
      <p v-if="!$v.email.required">Email is required</p>
    </div>

    <button type="submit">Submit</button>
  </div>
</template>

<script>
import { required, email } from 'vuelidate/lib/validators'

export default {
  data() {
    return {
      email: null,
    }
  },
  validations: {
    email: {
      required,
      email,
    },
  },
}
</script>

<style>
</style>
