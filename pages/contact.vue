<template>
  <v-row justify="center" class="d-flex justify-center mt-4">
    <v-col cols="md-6" class="d-flex justify-end">
      <v-col cols="md-8" class="lighten-5 mb-6">
        <div class="staticHero">
          <v-row align="end" class="black--text fill-height">
            <v-col>
              <v-container>
                <div
                  class="text-h5 font-weight-bold mb-2 headline"
                  style="color: #194f34"
                >
                  Fale Conosco
                </div>
                <div class="text" style="font-size: 14px; font-weight: 300">
                  Sinta-se livre para pedir detalhes, não salve nenhuma pergunta!
                </div>
              </v-container>
            </v-col>
          </v-row>
        </div>
        <div class="block">
          <v-container>
            <v-form ref="form" v-model="valid" lazy-validation>
              <v-text-field
                v-model="name"
                :rules="nameRules"
                label="Nome"
                required
              ></v-text-field>
              <v-text-field
                v-model="email"
                :rules="emailRules"
                label="Email"
                required
              ></v-text-field>
              <v-text-field
                v-model="subject"
                :rules="subjectRules"
                label="Assunto"
                required
              ></v-text-field>
              <v-textarea
                v-model="message"
                :rules="messageRules"
                label="Mensagem"
                required
              ></v-textarea>
              <v-btn
                :disabled="!valid"
                color="success"
                class="mr-4"
                @click="validate"
                >Enviar</v-btn
              >
              <v-btn color="error" class="mr-4" @click="reset">Resetar</v-btn>
            </v-form>
          </v-container>
        </div>
      </v-col>
    </v-col>

    <v-col cols="md-6">
      <v-row>
        <v-col cols="md-8 sm-4">
          <v-card-title class="text-h5 font-weight-bold mb-2 headline" style="color: #194f34">
            Nosso Endereço
          </v-card-title>
          <v-row>
            <v-col cols="12" class="pb-0">
              <v-icon class="mr-1 pl-4" style="color: #194f34">mdi-map-marker</v-icon>
              <span class="subheading">
                <strong style="color: #194f34">Endereço:</strong>
                Av. Afonso Pena 5723 Royal Park, CG MS</span>
            </v-col>
            <v-col cols="12" class="pb-0">
              <v-icon class="mr-1 pl-4" style="color: #194f34">
                mdi-phone
              </v-icon>
              <span class="subheading">
                  <strong style="color: #194f34">Telefone:</strong>
                +55 (67) 998081220
              </span>
            </v-col>
            <v-col cols="12" class="pb-0">
              <v-icon class="mr-1 pl-4" style="color: #194f34"> mdi-at </v-icon>
              <span class="subheading"
                ><strong style="color: #194f34">E-mail:</strong>
                <a href="mailto:internacionalagro@outlook.com">internacionalagro@outlook.com</a></span
              >
            </v-col>
          </v-row>
        </v-col>
        <v-col cols="md-8 sm-4">
          <v-card-title class="text-h5" style="color: #194f34">
            Horário Comercial
          </v-card-title>

          <v-icon class="mr-1 pl-4" style="color: #194f34">
            mdi-calendar-clock
          </v-icon>
          <span class="subheading">
            Segunda – Sexta – 09 às 18 horas
          </span>
        </v-col>
        <v-col cols="md-8 sm-4">
          <v-card-title class="text-h5" style="color: #194f34">
            Entrar em Contato
          </v-card-title>
          <v-row>
            <v-col cols="1">
              <v-icon class="mr-1 pl-4" style="color: #194f34">
                mdi-account-group
              </v-icon>
            </v-col>
            <v-col cols="11" class="pl-5">
              <span class="subheading">
                Nossa equipe está apta para atender suas solicitações, entre em contato pelo formulário ou telefone ou email ou faça-nos uma visita em nosso endereço.
              </span>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-col>

    <v-snackbar
      v-model="snackbar"
      timeout="3000"
    >
      Mensagem enviada com sucesso!
    </v-snackbar>
  </v-row>
</template>

<script>
export default {
  name: 'AContact',
  data: (instance) => ({
    valid: true,
    name: '',
    nameRules: [(v) => !!v || (instance.rules.nameRuleRequired ?? '')],
    email: '',
    emailRules: [
      (v) => !!v || (instance.rules.emailRuleRequired ?? ''),
      (v) => /.+@.+\..+/.test(v) || (instance.rules.emailRuleNotValid ?? ''),
    ],
    message: '',
    messageRules: [
      (v) => !!v || (instance.rules.messageRuleRequired ?? ''),
      (v) => (v && v.length >= 10) || (instance.rules.messageRuleSmall ?? ''),
    ],
    subject: '',
    subjectRules: [(v) => !!v || (instance.rules.subjectRuleRequired ?? '')],
    rules: {
        nameRuleRequired: 'Nome é obrigatório',
        emailRuleRequired: 'Email é obrigatório',
        emailRuleNotValid: 'Email deve ser válido',
        messageRuleRequired: 'Mensagem é obrigatório',
        messageRuleSmall: 'Mensagens devem ter mais de 10 caracteres',
        subjectRuleRequired: 'Assunto é obrigatório'
    }
  }),
  methods: {
    validate() {
      if (this.$refs.form.validate()) {
        this.snackbar = true
        this.reset()
      }
    },
    reset() {
      this.$refs.form.reset()
    },
  },
}
</script>
