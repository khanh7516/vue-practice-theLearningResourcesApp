<template>
    <base-card>
        <base-button @click="setSelectedTab('stored-resources')" :mode="stoBtnMode">Stored Button</base-button>
        <base-button @click="setSelectedTab('add-resource')" :mode="addBtnMode">Add Resource</base-button>
    </base-card>
    <keep-alive>
            <component :is="selectedTab"> </component>
    </keep-alive>

</template>

<script>
import StoredResources from './StoredResources.vue';
import AddResource from './AddResource.vue';
export default {
    components: {
        StoredResources,
        AddResource,
    },
    data() {
        return {
            selectedTab: 'stored-resources',

            storedResources: [
                {
                    id: "offical-guide",
                    title: "Offical Guide",
                    description: "The offical Vuejs doc",
                    link: "https://vuejs.org"
                },
                {
                    id: "google",
                    title: "Google",
                    description: "Learing to google...",
                    link: "https://google.org"
                }
            ],
        };
    },
    provide() {
        return {
            resources: this.storedResources,
            addNewResource: this.addNewResource,
            deleteRes: this.deleteRes
        };
    },
    computed: {
        stoBtnMode() {
            return this.selectedTab === 'stored-resources' ? null : 'flat';
        },
        addBtnMode() {
            return this.selectedTab === 'add-resource' ? null : 'flat';
        }
    },
    methods: {
        setSelectedTab(tab) {
            this.selectedTab = tab;
        },
        addNewResource(title, des, link) {
            const newRes = {
                id: new Date().toISOString(),
                title: title,
                description: des,
                link: link
            };
            this.storedResources.push(newRes);
            this.selectedTab = "stored-resources";
        },
        deleteRes(resId) {
            const deletedIndex = this.storedResources.findIndex((res) => res.id === resId);
            this.storedResources.splice(deletedIndex, 1);
        }
    }

}
</script>