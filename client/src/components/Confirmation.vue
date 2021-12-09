<template>
    <div class="alert alert-success alert-dismissible fade show" role="alert">
      <b-alert variant="success" show>{{ message }}</b-alert>
      Бутстрап подключен и работает
      <button type="button" class="close" data-dismiss="alert" aria-label="Close">
        <span aria-hidden="true">&times;</span>
      </button>
    </div>
</template>

<script>
export default {
  props: ['message'],
  name: 'Confirmation',
};
</script>
