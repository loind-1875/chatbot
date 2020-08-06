<template>
    <div class="container-fluid h-100">
        <div class="row justify-content-center h-100">
            <div class="col-md-8 col-xl-6 chat">
                <div class="card">
                    <div class="card-header msg_head">
                        <div class="d-flex bd-highlight">
                            <div class="img_cont">
                                <img src="https://static.turbosquid.com/Preview/001292/481/WV/_D.jpg" class="rounded-circle user_img" />
                                <span class="online_icon"></span>
                            </div>
                            <div class="user_info">
                                <span>Chat with Chồng yêu </span>
                            </div>
                        </div>
                    </div>
                    <div class="card-body msg_card_body">
                        <div class="d-flex justify-content-start mb-4">
                            <div class="img_cont_msg">
                                <img src="https://static.turbosquid.com/Preview/001292/481/WV/_D.jpg" class="rounded-circle user_img_msg" />
                            </div>
                            <div class="msg_cotainer">
                                Hi, how are you samim?
                                <span class="msg_time">8:40 AM, Today</span>
                            </div>
                        </div>
                        <div class="d-flex justify-content-end mb-4">
                            <div class="msg_cotainer_send">
                                You are welcome
                                <span class="msg_time_send">9:05 AM, Today</span>
                            </div>
                            <div class="img_cont_msg">
                                <img src="" class="rounded-circle user_img_msg" />
                            </div>
                        </div>
                    </div>
                    <div class="card-footer">
                        <div class="input-group">
                            <div class="input-group-append">
                                <span class="input-group-text attach_btn"><i class="fas fa-paperclip"></i></span>
                            </div>
                            <textarea name="" class="form-control type_msg" placeholder="Type your message..." v-model="message"></textarea>
                            <div class="input-group-append">
                                <span class="input-group-text send_btn" @click="submit">
                                    <i class="fas fa-location-arrow"></i>
                                </span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import axios from 'axios';

    export default {
        data: () => (
            {
                message: ''
            }
        ),
        methods: {
            submit () {
                axios.defaults.headers.common['Access-Control-Allow-Origin'] = '*';
                console.log(12)
                axios.post(`https://simsumi.herokuapp.com/api?text=${this.message}&lang=vi`, {}, {headers: {}})
                .then((res) => {
                    console.log(res);
                }).catch(err => {
                    console.log(err.response);
                  });
            }
        }
    }
</script>