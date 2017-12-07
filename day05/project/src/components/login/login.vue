<template>
    <div>
        <input type="text" v-model="username"/>
        <input type="password"  v-model="password"/>
        <input type="button" value="Login" @click="Login"/>
        <spinner v-show="show"></spinner>
    </div>
</template>

<script>
    import axios from 'axios';
    import spinner from '../spinner/spinner.vue'
    import request from 'superagent'
    import qs from 'qs'

    export default {
        data: function(){
            return {
                username: '',
                password: '',
                show: false
            }
        },
        methods: {
            Login: function(){
                // console.log(spinner);
                // this.show = true;
                // request.post('http://localhost/course/course-code/gz1706/vue/php/user.php').set('Content-Type', 'application/x-www-form-urlencoded; charset=UTF-8').send({username: this.username, password: this.password}).end((err, res) => {
                //     console.log(111);
                // })
                // axios.post('http://localhost/course/course-code/gz1706/vue/php/user.php', {username: this.username, password: this.password}).then(res => {
                //     console.log(this, res);
                //     // this.show = false;
                // })
                this.show = true;
                axios({
                    url: 'http://localhost/course/course-code/gz1706/vue/php/user.php',
                    method: 'post',
                    data: qs.stringify({username: this.username, password: this.password}),
                    headers: {
                        'Content-Type': 'application/x-www-form-urlencoded'
                    }
                }).then(res => {
                    this.show = false;
                    this.$router.push({name: 'student'});
                    // console.log(this)
                })
                //发起 ajax 请求
            }
        },
        components: {
            spinner: spinner
        }
    }
</script>