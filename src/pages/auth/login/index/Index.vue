<template>
    <page-container>
        <section class="hero is-fullheight is-dark is-bold">
            <app-messages></app-messages>
            <div class="hero-body">
                <div class="container">
                    <div class="columns is-vcentered">
                        <start-auth-form class="column is-4 is-offset-4"></start-auth-form>
                    </div>
                </div>
            </div>
        </section>
    </page-container>
</template>

<script>

import PageContainer from 'pages/auth/login/container/Container.vue';
import AppMessages from 'message/components/message/AppMessages.vue';
import StartAuthForm from 'auth/components/forms/login/StartAuthForm.vue';

export default {
    data() {
        return {
            booted: false
        };
    },
    components: {
        PageContainer,
        AppMessages,
        StartAuthForm
    }
};
</script>

<style type="text/css">

</style>
