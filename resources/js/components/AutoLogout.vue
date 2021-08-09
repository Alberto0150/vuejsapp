<template>
    
</template>
<script>
    export default{
        data: function () {
            return{
                events: ['click', 'mousemove', 'scroll', 'keypress', 'load'],

                theTimer:null,
            }
        },

        mounted() {
            this.events.forEach(function (event_name){
                window.addEventListener(event_name, this.reset);
            }, this
            )},

        methods:{
            setTimer: function(){
                this.theTimer = setTimeout(this.LogoutUser, 20 * 1000);
            },

            LogoutUser:function(){
                $("#logout-form").submit();
                alert('You Have been Logout');

            },
            reset: function(){
                clearTimeout(this.theTimer);
                this.setTimer();
            }
        }
    }
</script>
