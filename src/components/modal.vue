<template>
	<div>
		<div class="md-modal modal-msg md-modal-transition md-show" v-show="mdShow">
          <div class="md-modal-inner">
            <div class="md-top">
              <button class="md-close" @click="closeModal">Close</button>
            </div>
            <div class="md-content">
              <div class="confirm-tips">
                <slot name="message"></slot>
              </div>
              <div class="login-wrap">
                 <slot name="btnGroup"></slot>
              </div>
            </div>
          </div>
	   </div>
	   <div class="md-overlay" v-show="mdShow" @click="closeModal"></div>
	</div>
</template>
<script type="text/javascript">
	export default{
		props:["mdShow"],
		data(){
			return {
				modalFlag:true
			}
		},
		methods:{
		  closeModal(){
		    this.$emit("close");
		  }
		}
	}
</script>