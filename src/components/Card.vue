
    <template>
  <div class="card">
    <slot name="header"></slot>
    <slot name="body"></slot>
  </div>
</template>

<script>
export default {
  name: 'CardComp'
}
</script>

<style>
.card {
  border: 1px solid #ccc;
  border-radius: 4px;
  padding: 20px;
  margin-bottom: 20px;
}
</style>