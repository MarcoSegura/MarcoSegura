<template>
  <div>
    <div
      class="alert alert-danger"
      role="alert"
      v-if="getStatusRequest === 401"
    >
      Usuario y/o contraseña incorrecta, vuelva a intentarlo
    </div>
    <div
      class="alert alert-danger"
      role="alert"
      v-if="getStatusRequest === 422"
    >
      Asegurese de llenar todos los campos con el formato requerido
    </div>
    <div
      class="alert alert-success"
      role="alert"
      v-if="getStatusRequest === 200"
    >
      Sesión inciada exitosamente
    </div>

    <div class="d-flex justify-content-center align-items-center mt-5 mb-5">
      <img src="@/assets/logo-aula.png" class="mx-1" style="width: 55%" />
      <!-- <div class="text-logo mt-5 mb-5">IPSSOMA</div> -->
    </div>

    <b-form @submit.prevent="singin">
      <div class="mt-5">
        <b-form-group class="my-2 subtitle text-white" label="Usuario *">
          <b-form-input
            class="rounded-pill mt-2"
            type="text"
            v-model="form.username"
            placeholder="Ingrese su usuario"
            required
          ></b-form-input>
        </b-form-group>
      </div>

      <div class="mt-5">
        <b-form-group class="my-2 subtitle text-white" label="Contraseña *">
          <b-form-input
            class="rounded-pill holder-form mt-2"
            type="password"
            v-model="form.password"
            placeholder="Ingrese su contraseña"
            required
          ></b-form-input>
        </b-form-group>
      </div>

      <b-form-group>
        <b-form-checkbox-group>
          <b-form-checkbox
            class="subtitle text-white mt-4"
            value="me"
            name="checkbox-validation"
            >Recuerdame</b-form-checkbox
          >
        </b-form-checkbox-group>
      </b-form-group>

      <b-button class="submit-iniciar rounded-pill mb-5" type="submit" block
        >Ingresar</b-button
      >
    </b-form>

    <div class="row text-center mt-5 justify-content-center mb-3 items">
      <div class="col-2">
        <a href="https://www.facebook.com/ipssoma/" target="_blank">
          <img
            src="@/views/auth/icons/facebook-icon.png"
            style="width: 100%; height: auto"
          />
        </a>
      </div>
      <div class="col-2">
        <a href="https://www.instagram.com/ipssoma/" target="_blank">
          <img
            src="@/views/auth/icons/instagram-icon.png"
            style="width: 100%; height: auto"
          />
        </a>
      </div>
      <div class="col-2">
        <a
          href="https://www.linkedin.com/company/instituto-peruano-ssoma/"
          target="_blank"
        >
          <img
            src="@/views/auth/icons/linked-icon.png"
            style="width: 100%; height: auto"
          />
        </a>
      </div>
      <div class="col-2">
        <a href="https://ipssoma.com" target="_blank">
          <img
            src="@/views/auth/icons/web-icon.png"
            style="width: 100%; height: auto"
          />
        </a>
      </div>
      <div class="col-2">
        <a
          href="https://www.youtube.com/channel/UCvYRjy5-aijIB3tZK-lE6gg"
          target="_blank"
        >
          <img
            src="@/views/auth/icons/youtube-icon.png"
            style="width: 100%; height: auto"
          />
        </a>
      </div>
    </div>
    <div class="text-center">
      <h5 style="font-size: 0.7em; color: #989898">
        Copyright &copy; {{ year }}. Todos los derechos reservados para IPSSOMA
      </h5>
    </div>
  </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";
export default {
  name: "FormLogin",
  data() {
    return {
      form: {
        username: null,
        password: null,
      },
      year: "",
    };
  },
  props: {},
  methods: {
    ...mapActions("user", {
      actionUser: "actionUser",
    }),

    singin() {
      this.actionUser(this.form);
    },

    setYear() {
      this.year = new Date().getFullYear();
    },
  },
  computed: {
    ...mapGetters("user", ["getStatusRequest"]),
  },
  created() {
    this.setYear();
  },
};
</script>
<style>
a > img {
  max-width: 45px;
}

:root {
  --color-prin: #1ae800;
}
.submit-iniciar {
  background: var(--seventh-color-green) !important;
  border: none !important;
  color: white !important;
}
.submit-iniciar:hover {
  background: var(--eighth-color-green) !important;
}
.subtitle {
  font-size: 1em;
}
.holder-form {
  border: 1px solid #35424a;
  border-radius: 30px;
  font-size: 12px;
  padding: 8px 10px;
  padding-left: 21px;
}
.form-values {
  margin-bottom: 30px;
}
.remember {
  font-size: 12px;
}
.remember input {
  align-self: center;
}
.change {
  color: var(--color-prin);
  font-size: 12px;
}
.loguear {
  border: 1px;
  background-color: var(--color-prin);
  border-radius: 30px;
  width: 100%;
  height: 50px;
}
.form-check {
  margin-bottom: 25px;
  flex-flow: row wrap;
}
.form-check > a {
  font-weight: bold;
}
</style>
