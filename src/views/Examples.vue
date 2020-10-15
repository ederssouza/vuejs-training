<template>
  <div class="container">
    <div v-if="slug === 'componente-basico'" >
      <h1>Componente básico</h1>
      <BasicComponent />
    </div>

    <div v-if="slug === 'componente-ciclo-de-vida'" >
      <h1>Ciclo de vida de um componente</h1>
      <LifeCycle />
    </div>

    <div v-if="slug === 'diretiva-v-text'" >
      <h1>Diretiva v-text</h1>
      <DirectiveVText />
    </div>

    <div v-if="slug === 'diretiva-v-html'" >
      <h1>Diretiva v-html</h1>
      <DirectiveVHtml />
    </div>

    <div v-if="slug === 'diretiva-v-show'" >
      <h1>Diretiva v-show</h1>
      <DirectiveVShow />
    </div>

    <div v-if="slug === 'diretiva-v-if'" >
      <h1>Diretiva v-if</h1>
      <DirectiveVIf />
    </div>

    <div v-if="slug === 'diretiva-v-else'" >
      <h1>Diretiva v-else</h1>
      <DirectiveVElse />
    </div>

    <div v-if="slug === 'diretiva-v-else-if'" >
      <h1>Diretiva v-else-if</h1>
      <DirectiveVElseIf />
    </div>

    <div v-if="slug === 'diretiva-v-for'" >
      <h1>Diretiva v-for</h1>
      <DirectiveVFor />
    </div>

    <div v-if="slug === 'diretiva-v-on'" >
      <h1>Diretiva v-on</h1>
      <DirectiveVOn />
    </div>

    <div v-if="slug === 'diretiva-v-bind'" >
      <h1>Diretiva v-bind</h1>
      <DirectiveVBind />
    </div>

    <div v-if="slug === 'diretiva-v-model'" >
      <h1>Diretiva v-model</h1>
      <DirectiveVModel />
    </div>

    <div v-if="slug === 'metodos'">
      <h1>Criando métodos e disparando eventos</h1>
      <Methods />
    </div>

    <div v-if="slug === 'metodos-assíncronos'">
      <h1>Métodos assíncronos</h1>
      <Api />
    </div>

    <div v-if="slug === 'props'">
      <h1>Passando props para um componente</h1>
      <Props />
    </div>

    <div v-if="slug === 'evento-emit'">
      <h1>Emitindo eventos <code>vm.$emit(eventName, [...args])</code></h1>
      <Alert />
    </div>

    <div v-if="slug === 'filtros'">
      <h1>Filtros</h1>
      <Filters />
    </div>
  </div>
</template>

<script>
import BasicComponent from '../components/examples/BasicComponent'
import LifeCycle from '../components/examples/LifeCycle'
import DirectiveVText from '../components/examples/DirectiveVText'
import DirectiveVHtml from '../components/examples/DirectiveVHtml'
import DirectiveVShow from '../components/examples/DirectiveVShow'
import DirectiveVIf from '../components/examples/DirectiveVIf'
import DirectiveVElse from '../components/examples/DirectiveVElse'
import DirectiveVElseIf from '../components/examples/DirectiveVElseIf'
import DirectiveVFor from '../components/examples/DirectiveVFor'
import DirectiveVOn from '../components/examples/DirectiveVOn'
import DirectiveVBind from '../components/examples/DirectiveVBind'
import DirectiveVModel from '../components/examples/DirectiveVModel'
import Methods from '../components/examples/Methods'
import Props from '../components/examples/props'
import Alert from '../components/examples/alert'
import Filters from '../components/examples/Filters'
import Api from '../components/examples/api'

export default {
  name: 'Examples',
  components: {
    BasicComponent,
    LifeCycle,
    DirectiveVText,
    DirectiveVHtml,
    DirectiveVShow,
    DirectiveVIf,
    DirectiveVElse,
    DirectiveVElseIf,
    DirectiveVFor,
    DirectiveVOn,
    DirectiveVBind,
    DirectiveVModel,
    Methods,
    Props,
    Alert,
    Filters,
    Api
  },
  computed: {
    slug () {
      return this.$route.params.slug
    }
  }
}
</script>
