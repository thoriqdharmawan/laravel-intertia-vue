<script setup>
import { useForm } from "@inertiajs/vue3";
import TextInput from "../Components/TextInput.vue";

const form = useForm({
  email: null,
  password: null,
  remember: null
});

const submit = () => {
  form.post(route("login"), {
    onError: () => form.reset("password", 'remember'),
  });
};
</script>

<template>

  <Head title="Login"></Head>

  <h1 class="title">Login to your account</h1>

  <div class="w-2/4 mx-auto">
    <form @submit.prevent="submit">
      <TextInput name="email" v-model="form.email" :message="form.errors.email" type="email" id="email" />
      <TextInput name="password" v-model="form.password" :message="form.errors.password" type="password"
        id="password" />

      <div class="flex items-center justify-between">
        <div class="flex items-center gap-2">
          <input type="checkbox" v-model="form.remember" id="remember" />
          <label for="remember">Remember me</label>
        </div>

        <p class="text-slate-600 mb-2">
          Need an account? <a :href="route('register')" class="text-link">register</a>
        </p>
      </div>

      <div>
        <button class="primary-btn" :disabled="form.processing">
          Login
        </button>
      </div>
    </form>
  </div>
</template>
