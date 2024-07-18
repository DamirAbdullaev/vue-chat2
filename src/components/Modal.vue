<template>
    <div class="modal">
        <div class="modal__block">
            <h2 class="modal__block-title">Отправить картинку</h2>
            
            <div class="modal__block_inputs">
                <label>
                    <span>URL</span>
                    <input placeholder="URL" type="text">
                </label>
                <label>
                    <span>Комментарий</span>
                    <input placeholder="Комментарий" type="text">
                </label>
            </div>

            <div class="modal__block_btn">
                <button class="cancel">Отмена</button>
                <button class="send">ОТПРАВИТЬ</button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>

</style>