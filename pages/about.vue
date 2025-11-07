<template>
  <div>
    <h2>About</h2>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit.
      Consectetur consequatur cupiditate debitis,
      distinctio ea et facere facilis inventore iure,
      iusto odit omnis perspiciatis provident quibusdam,
      ratione recusandae rerum sequi?
    </p>
    <div>{{ data }}</div>
  </div>
</template>

<script setup>
  // const { data } = await useFetch('/api/ninja?name=mario')
  const { data } = await useFetch('/api/ninja?name=minh', {
    method: 'post',
    body: {age: 26}
  })

  // const { data } = await useFetch('/api/ninja')

  // const { data } = await useFetch('/api/currency/GBP')
</script>

<style scoped>
h2 {
  margin-bottom: 20px;
  font-size: 36px;
}
p {
  margin: 20px 0;
}
</style>