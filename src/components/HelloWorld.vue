<template>
    <v-form v-model="valid">
        <v-container text-xs-center>
            <v-layout xs8>
                <v-text-field
                        v-model="firstname"
                        :rules="nameRules"
                        :counter="10"
                        label="First name"
                        required
                ></v-text-field>
            </v-layout>

            <v-layout xs8>
                <v-text-field
                        v-model="lastname"
                        :rules="nameRules"
                        :counter="10"
                        label="Last name"
                        required
                ></v-text-field>
            </v-layout>

            <v-layout xs8>
                <v-text-field
                        v-model="email"
                        :rules="emailRules"
                        label="E-mail"
                        required
                ></v-text-field>
            </v-layout>
        </v-container>
    </v-form>
</template>
<script>
    export default {
        data: () => ({
            valid: false,
            firstname: '',
            lastname: '',
            nameRules: [
                v => !!v || 'Name is required',
                v => v.length <= 10 || 'Name must be less than 10 characters'
            ],
            email: '',
            emailRules: [
                v => !!v || 'E-mail is required',
                v => /.+@.+/.test(v) || 'E-mail must be valid'
            ]
        })
    }
</script>