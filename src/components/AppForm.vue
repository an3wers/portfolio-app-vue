<template>
  <div class="col-lg-4 mb-3">
    <div class="card">
      <div class="card-body">
        <form>
          <select class="form-select mb-3" aria-label="selector">
            <option value="1">Имя</option>
            <option value="2">Должность</option>
            <option value="3">Аватар</option>
            <option value="3">Описание</option>
          </select>
          <textarea class="form-control mb-3" id="textarea" rows="3"></textarea>
          <button type="submit" class="btn btn-primary">Сохранить</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>
