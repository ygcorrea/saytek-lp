<template>
  <v-app>
    <v-app-bar flat color="black">
      <v-img :src="imageLink.logo" alt="Vuetify.js" height="56"></v-img>
      <v-spacer></v-spacer>
    </v-app-bar>

    <v-main>
      <section>
        <v-parallax :src="imageLink.sub_main" height="600">
          <div class="header" style="color: white">
            <h1
              class="mb-2 display-1 text-xs-center"
              style="font-weight: 900; text-shadow: 3px 2px rgba(0, 0, 0, 0.7)"
            >
              Transforme suas ideias em realidade
            </h1>
            <div
              class="subheading mb-3 text-xs-center"
              style="font-weight: 900; text-shadow: 2px 2px rgba(0, 0, 0, 0.7)"
            >
              Consultoria completa em TI e design UX/UI para tirar seu projeto
              do papel
            </div>
            <v-btn class="blue lighten-2 mt-5" dark large href="/contact">
              Contrate-nos
            </v-btn>
          </div>
        </v-parallax>
      </section>

      <section>
        <v-container class="my-5 text-center">
          <h2 class="headline">Do conceito à execução</h2>
          <span class="subheading">
            Nossa equipe especializada em TI, UX/UI e design gráfico está pronta
            para transformar suas ideias em soluções digitais de sucesso.
          </span>
          <v-row class="mt-5">
            <v-col cols="12" md="4">
              <v-card elevation="0" class="transparent">
                <v-card-title class="justify-center">
                  <v-icon size="large" color="blue lighten-2">mdi-earth</v-icon>
                </v-card-title>
                <v-card-text>
                  Soluções globais: conectamos sua empresa ao mundo digital,
                  criando plataformas que expandem sua presença online e
                  potencializam seu crescimento.
                </v-card-text>
              </v-card>
            </v-col>
            <v-col cols="12" md="4">
              <v-card elevation="0" class="transparent">
                <v-card-title class="justify-center">
                  <v-icon size="large" color="blue lighten-2">mdi-flash</v-icon>
                </v-card-title>
                <v-card-text>
                  Agilidade e inovação: desenvolvemos projetos com rapidez,
                  sempre incorporando as últimas tendências de tecnologia e
                  design para manter sua marca à frente.
                </v-card-text>
              </v-card>
            </v-col>
            <v-col cols="12" md="4">
              <v-card elevation="0" class="transparent">
                <v-card-title class="justify-center">
                  <v-icon size="large" color="blue lighten-2">mdi-share</v-icon>
                </v-card-title>
                <v-card-text>
                  Experiência personalizada: nossos especialistas em UX/UI
                  garantem que cada interface seja desenhada para oferecer a
                  melhor experiência ao usuário, aumentando a satisfação e
                  engajamento.
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </section>

      <section>
        <v-parallax :src="imageLink.main" height="380">
          <div class="d-flex flex-column align-center justify-center">
            <h3 class="white--text mb-3 text-center">
              Projetos sob medida para suas necessidades
            </h3>
            <em class="white--text">
              Seja no desenvolvimento de aplicativos, sites ou soluções
              gráficas, oferecemos o suporte que você precisa para alcançar o
              sucesso.
            </em>
            <v-btn class="blue lighten-2 mt-5" dark large href="/contact">
              Fale conosco
            </v-btn>
          </div>
        </v-parallax>
      </section>

      <!-- Seção de Projetos Realizados -->
      <section>
        <v-container class="my-5 text-center">
          <h3 class="headline">Projetos Realizados</h3>
          <p>
            Aqui estão alguns dos projetos que ajudamos a transformar em
            realidade:
          </p>

          <v-carousel hide-delimiters height="400" cycle>
            <v-carousel-item
              v-for="(group, index) in projectGroups"
              :key="index"
            >
              <v-row>
                <v-col
                  cols="12"
                  md="4"
                  v-for="(project, idx) in group"
                  :key="idx"
                >
                  <v-card elevation="2" class="mx-auto" max-width="400">
                    <v-img :src="project.image" height="200"></v-img>
                    <v-card-title>{{ project.title }}</v-card-title>
                    <v-card-text>{{ project.description }}</v-card-text>
                  </v-card>
                </v-col>
              </v-row>
            </v-carousel-item>
          </v-carousel>
        </v-container>
      </section>
      <v-footer
        color="#24004b"
        class="d-flex align-center white--text justify-center"
      >
        <div class="text-center">
          Feito com 💜 por SAYTEK
          <v-icon>mdi</v-icon>
          Copyright © 2024 Todos os direitos reservados
        </div>
      </v-footer>
    </v-main>
  </v-app>
</template>

<script>
import { ref } from 'vue';
import { computed } from 'vue';
export default {
  setup() {
    const title = ref('Consultoria de TI e Design');
    const imageLink = ref({
      main: 'https://cdn.pixabay.com/photo/2017/03/28/22/55/night-photograph-2183637_1280.jpg',
      sub_main:
        'https://cdn.pixabay.com/photo/2017/08/10/00/40/stars-2616537_1280.jpg',
      logo: 'https://github.com/user-attachments/assets/a04b8105-7a0c-4725-8c40-66410c830e4e',
      social_cover:
        'https://cdn.pixabay.com/photo/2021/11/11/09/12/lighthouse-6785763_1280.jpg',
    });
    const projects = ref([
      {
        title: 'Website Corporativo XYZ',
        description:
          'Desenvolvimento completo do site com foco em SEO e design responsivo para ampliar a presença online da empresa XYZ.',
        image: 'https://via.placeholder.com/400x300',
      },
      {
        title: 'Aplicativo de Gestão Financeira ABC',
        description:
          'Aplicativo mobile com design intuitivo e usabilidade avançada, permitindo uma gestão eficiente de finanças pessoais.',
        image: 'https://via.placeholder.com/400x300',
      },
      {
        title: 'Identidade Visual para Startup DEF',
        description:
          'Criação de logotipo, paleta de cores e materiais de marketing para a startup DEF, destacando-se no mercado de inovação.',
        image: 'https://via.placeholder.com/400x300',
      },
      {
        title: 'E-commerce para Empresa GHI',
        description:
          'Desenvolvimento de plataforma e-commerce para impulsionar as vendas online com uma experiência de usuário aprimorada.',
        image: 'https://via.placeholder.com/400x300',
      },
      {
        title: 'Plataforma de Educação Online JKL',
        description:
          'Desenvolvemos uma plataforma intuitiva para cursos online, aumentando o engajamento de alunos e instrutores.',
        image: 'https://via.placeholder.com/400x300',
      },
      {
        title: 'Aplicativo de Saúde MNO',
        description:
          'Aplicativo desenvolvido para monitoramento de saúde e agendamento de consultas de forma prática e ágil.',
        image: 'https://via.placeholder.com/400x300',
      },
    ]);

    const projectGroups = computed(() => {
      const groups = [];
      for (let i = 0; i < projects.value.length; i += 3) {
        groups.push(projects.value.slice(i, i + 3));
      }
      return groups;
    });

    const email = ref('');
    const emailRules = [
      (v) => !!v || 'E-mail é obrigatório',
      (v) =>
        /^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/.test(v) ||
        'E-mail deve ser válido',
    ];
    const subscribed = ref(false);

    const subscribe = () => {
      subscribed.value = !subscribed.value;
    };

    return {
      title,
      imageLink,
      email,
      emailRules,
      subscribed,
      subscribe,
      projects,
      projectGroups,
    };
  },
};
</script>

<style scoped>
.header {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  flex-direction: column;
  text-align: center;
}
.finedTitle {
  font-weight: 900;
  text-shadow: 2px 2px #000000;
}

.social-icon {
  font-size: 21px;
  color: white;
}
:deep(.v-img__img--cover) {
  -o-object-fit: initial !important;
  object-fit: initial !important;
}
</style>
