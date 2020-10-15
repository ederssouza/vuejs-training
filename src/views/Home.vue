<template>
  <div>
    <div class="container">
      <h1>Exemplos</h1>
      <ul>
        <li>
          <router-link :to="{ name: 'Examples', params: { slug: 'componente-basico' } }">
            1. Componente básico
          </router-link>
        </li>
        <li>
          <router-link :to="{ name: 'Examples', params: { slug: 'componente-ciclo-de-vida' } }">
            2. Ciclo de vida de um componente
          </router-link>
        </li>
        <li>
          3. Diretivas
          <ul>
            <li>
              <router-link :to="{ name: 'Examples', params: { slug: 'diretiva-v-text' } }">
                <code>v-text</code>
              </router-link>
            </li>
            <li>
              <router-link :to="{ name: 'Examples', params: { slug: 'diretiva-v-html' } }">
                <code>v-html</code>
              </router-link>
            </li>
            <li>
              <router-link :to="{ name: 'Examples', params: { slug: 'diretiva-v-show' } }">
                <code>v-show</code>
              </router-link>
            </li>
            <li>
              <router-link :to="{ name: 'Examples', params: { slug: 'diretiva-v-if' } }">
                <code>v-if</code>
              </router-link>
            </li>
            <li>
              <router-link :to="{ name: 'Examples', params: { slug: 'diretiva-v-else' } }">
                <code>v-else</code>
              </router-link>
            </li>
            <li>
              <router-link :to="{ name: 'Examples', params: { slug: 'diretiva-v-else-if' } }">
                <code>v-else-if</code>
              </router-link>
            </li>
            <li>
              <router-link :to="{ name: 'Examples', params: { slug: 'diretiva-v-for' } }">
                <code>v-for</code>
              </router-link>
            </li>
            <li>
              <router-link :to="{ name: 'Examples', params: { slug: 'diretiva-v-on' } }">
                <code>v-on</code> ou <code>@</code>
              </router-link>
            </li>
            <li>
              <router-link :to="{ name: 'Examples', params: { slug: 'diretiva-v-bind' } }">
                <code>v-bind</code> ou <code>:</code>
              </router-link>
            </li>
            <li>
              <router-link :to="{ name: 'Examples', params: { slug: 'diretiva-v-model' } }">
                <code>v-model</code>
              </router-link>
            </li>
          </ul>
        </li>
        <li>
          4. Métodos
          <ul>
            <li>
              <router-link :to="{ name: 'Examples', params: { slug: 'metodos' } }">
                Criando métodos e disparando eventos
              </router-link>
            </li>
            <li>
              <router-link :to="{ name: 'Examples', params: { slug: 'metodos-assíncronos' } }">
                Métodos assíncronos
              </router-link>
            </li>
          </ul>
        </li>
        <li>
          <router-link :to="{ name: 'Examples', params: { slug: 'props' } }">
            5. Passando props para um componente
          </router-link>
        </li>
        <li>
          <router-link :to="{ name: 'Examples', params: { slug: 'evento-emit' } }">
            6. Emitindo eventos para o componente pai
          </router-link>
        </li>
        <li>
          <router-link :to="{ name: 'Examples', params: { slug: 'filtros' } }">
            7. Filtros
          </router-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  components: {
  }
}
</script>

<style lang="scss" scoped>
code {
  font-size: 87.5%;
  color: #e83e8c;
  word-wrap: break-word;
}
</style>
