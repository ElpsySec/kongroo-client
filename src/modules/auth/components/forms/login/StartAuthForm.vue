<template lang="html">
    <div class="">
        <h1 class="title">
            Login
        </h1>
        <div class="box">
            <label class="label">Email</label>
            <p class="control">
                 <input class="input" v-model="creds.email" type="text" placeholder="jsmith@example.org">
            </p>
            <errors :errors="authErrors" v-if="hasAuthErrors"></errors>
            <hr>
            <p class="control">
                <router-link class="button is-default" :to="{name: 'article.index'}">
                     Go Back
                </router-link>
                <!-- <span></span> -->
               <button class="button is-primary is-pulled-right" @click="startLogin">
                   Next
               </button>
            </p>
        </div>
    </div>

</template>

<script>
import Errors from "error/components/error/Errors";

export default {
    data() {
        return {
            creds: {
                email: 'admin@example.com'
            }
        }
    },
    methods: {
        startLogin() {
            this.$store.dispatch('auth/actions/startAuth', {email: this.creds.email}).then((tokens) => {
                
            }).catch(() => {

            });
        }
    },
    computed: {
        hasAuthErrors() {
            return this.authErrors.length > 0;
        },
        authErrors() {
            if (! this.errors) {
                return [];
            }
            return this.errors.filter((err) => {
                return err.bag === 'auth';
            })
        },
        errors() {
            return this.$store.getters['error/getters/errors']
        }
    },
    components: {
        Errors
    }
}
</script>

<style lang="css">
</style>
