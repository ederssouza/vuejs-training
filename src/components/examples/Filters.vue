<template>
  <div>
    <div>
      <strong>CNPJ:</strong> {{ '00000000000191' | cnpj }}
    </div>
    <div>
      <strong>Celular:</strong> {{ '11988887777' | phone }}
    </div>
    <div>
      <strong>Telefone:</strong> {{ '1144443333' | phone }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'Filters',
  filters: {
    cnpj (str = '') {
      return String(str).replace(/^(\d{2})(\d{3})(\d{3})(\d{4})(\d{2})$/, '$1.$2.$3/$4-$5')
    },

    phone (str = '') {
      return String(str).replace(/^(\d{2})(\d{4,5})(\d{4})$/, '($1) $2-$3')
    }
  }
}
</script>
