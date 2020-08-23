<template>
    <div class="container">
        <form>
            <div class="row" id="formDiv" v-if="!formSubmitted">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <form>
                        <fullName v-model="fullName" @sendName="data"></fullName>

                        <div class="form-group">
                            <label for="email"> Email </label>
                                <input type="text" id="email" v-model="email" class="form-control">
                        </div>
                        <div class="form-group">
                            <label for="password"> Password </label>
                                <input type="password" id="password" v-model="password" class="form-control">
                        </div>
                        <div class="form-group">
                            <label for="storeData"> Yes </label>
                                <input type="radio" id="yes" value=true v-model="storeData">
                            <label for="storeData"> No </label>
                                <input type="radio" id="no" value=false v-model="storeData">
                        </div>
                        <hr>
                        <button class="btn btn-primary" @click="formSubmitted = true"> Submit </button>
                    </form>

                    <!-- Exercise 2 -->
                    <!-- Only display the Form if it has NOT been submitted -->
                    <!-- Display the Data Summary ONCE the Form HAS been submitted -->

                    <!-- Exercise 3 -->
                    <!-- Edit the Example from above and create a custom "Full Name" Control -->
                    <!-- which still holds the First Name and Last Name Input Field -->
                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="formSubmitted" id="showData">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{ fullName }} </p>
                        <p>Mail: {{ email }} </p>
                        <p>Password: {{ password }} </p>
                        <p>Store in Database?: {{ formSubmitted }} </p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        components: { FullName: () => import("./components/fullName")},
        data() {
            return {
                fullName: "",
                email: "",
                password: "",
                storeData: false,
                formSubmitted: false
            }
        }
    }
</script>

<style>
</style>
