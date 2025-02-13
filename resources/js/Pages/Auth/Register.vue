<script setup>
import { useForm } from "@inertiajs/vue3";
import TextInput from "../Components/TextInput.vue";

const form = useForm({
  name: null,
  email: null,
  password: null,
  password_confirmation: null,
});

const submit = () => {
  form.post(route("register"), {
    onError: () => form.reset("password", "password_confirmation"),
  });
};
</script>

<template>

  <Head title="Register"></Head>

  <h1 class="title">Register a new account</h1>

  <div class="w-2/4 mx-auto">
    <form @submit.prevent="submit">
      <TextInput name="name" v-model="form.name" :message="form.errors.name" id="name" />
      <TextInput name="email" v-model="form.email" :message="form.errors.email" type="email" id="email" />
      <TextInput name="password" v-model="form.password" :message="form.errors.password" type="password"
        id="password" />
      <TextInput name="confirm password" v-model="form.password_confirmation" type="password"
        id="password_confirmation" />
      <div>
        <p class="text-slate-600 mb-2">
          Already a user? <a href="#" class="text-link">Login</a>
        </p>
        <button class="primary-btn" :disabled="form.processing">
          Login
        </button>
      </div>
    </form>
  </div>
</template>
