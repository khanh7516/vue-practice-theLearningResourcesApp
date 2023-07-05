<template>
    <base-dialog v-if="isInvalidValue" title="Invalid Input" @close="confirmErr">
        <template #default>
            <p>Please check all input!!!</p>
        </template>
        <template #actions>
            <base-button @click="confirmErr"> OK</base-button>
        </template>
    </base-dialog>
    <base-card>
        <form @submit.prevent="submitData">
            <div class="form-control">
                <label for="title">Title</label>
                <input name="title" id="title" type="title" v-model="enteredTitle">
            </div>
            <div class="form-control">
                <label for="des">Description</label>
                <textarea name="des" id="des" rows="3" v-model="enteredDes"> </textarea>
            </div>
            <div class="form-control">
                <label for="link">Link</label>
                <input name="link" id="link" type="url" v-model="enteredLink">
            </div>
            <div>
                <base-button type="submit">ADD</base-button>
            </div>
        </form>
    </base-card>
</template>

<script>
export default {
    inject: ["addNewResource"],
    data() {
        return {
            enteredTitle: '',
            enteredDes: '',
            enteredLink: '',
            isInvalidValue: false
        }
    },
    methods: {
        submitData() {
            if(this.enteredTitle.trim()=== '' || this.enteredDes.trim() === "" || this.enteredLink.trim() === '') {
                this.isInvalidValue = true;
                return;
            }
            this.addNewResource(this.enteredTitle, this.enteredDes, this.enteredLink);
            this.enteredTitle = "";
            this.enteredDes = "";
            this.enteredLink = "";
        },
        confirmErr() {
            this.isInvalidValue = false;
        }
    }
}
</script>

<style scoped>
    label {
        display: block;
        margin: 0 0 0.5rem 0;
    }
    input, textarea {
        display: block;
        width: 100%;
        padding: 0.5rem;
        margin: 0 0 1rem 0;
        border: 0.1rem solid orange;
    }

</style>