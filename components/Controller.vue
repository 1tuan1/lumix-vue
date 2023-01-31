<template>
  <div>
    <button class="btn btn-primary" @click="modalToggle">toggle modal</button>
    <div ref="modalMain" class="modal fade" id="modal-main">
      <div class="modal-dialog modal-dialog-centered" style="max-width: 600px">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="exampleModalLabel">Hello world!</h5>
            <button
                class="btn-close"
                data-bs-dismiss="modal"
                aria-label="Close"
            ></button>
          </div>
          <div class="modal-body p-4">Hello bootstrap and nuxt</div>
          <div class="modal-footer">
            <button class="btn btn-outline-secondary" data-bs-dismiss="modal">
              Close
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
  <hr/>
  <div>
    <button type="button" class="btn btn-primary" @click="toastShow">Show live toast</button>
    <div class="toast-container position-fixed bottom-0 end-0 p-3">
      <div ref="toastBtn" id="liveToast" class="toast" role="alert" aria-live="assertive" aria-atomic="true">
        <div class="toast-header">
          <img src="..." class="rounded me-2" alt="...">
          <strong class="me-auto">Bootstrap</strong>
          <small>11 mins ago</small>
          <button type="button" class="btn-close" data-bs-dismiss="toast" aria-label="Close"></button>
        </div>
        <div class="toast-body">
          Hello, world! This is a toast message.
        </div>
      </div>
    </div>
  </div>
</template>
<script setup lang="ts">
import {ComponentPublicInstance, ref} from 'vue'
import type {Modal, Toast} from 'bootstrap'

const modalMain = ref<ComponentPublicInstance<HTMLInputElement> | string>('')
const toastBtn = ref<ComponentPublicInstance<HTMLInputElement> | string>('')
let modal: Modal
let toast: Toast

const modalToggle = () => {
  modal.toggle()
}

const toastShow = () => {
  toast.show()
}

onMounted(() => {
  const {$bootstrap} = useNuxtApp()
  console.log(toastBtn)
  modal = new $bootstrap.Modal(modalMain.value)
  toast = new $bootstrap.Toast(toastBtn.value)
})
</script>
<style lang="scss"></style>