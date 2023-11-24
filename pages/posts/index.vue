<template>
    <Default>
        <template>
            <div class="header">

                <div>
                    <Button label="NEW POST" class="p-button-raised p-button-success"  icon="pi pi-plus" />
                </div>
                <div>
                    <InputText type="text" v-model="searchTerm" placeholder="Search Post"></InputText>
                </div>
               
            </div>

            <div class="posts">

                <span v-for="post in posts" :key="post.id">
                    <Card class="post-card" >
                        <template #title> 
                          <h2>  <i class="pi pi-user"></i> Kelvin Mukotso </h2> 
                            {{ post.title }}
                        </template>
                        <template #content>
                            <div class="flex">
                                <img src="../../static/images/old.jpeg"/>
                                <img src="../../static/images/old.jpeg"/>
                                <img src="../../static/images/old.jpeg"/>
                                <img src="../../static/images/old.jpeg"/>
                            </div>
                            <p>{{ post.description }}</p>
                        </template>

                        <template #footer>
                            <Button icon="pi pi-thumbs-up" class="p-button-rounded p-button-danger" /> <span class="bold">2.8K Likes</span>

                            <Button @click="showComments()" icon="pi pi-comment" class="p-button-rounded p-button-success" /> 1.8K Comments

                            <Button icon="pi pi-reply" class="p-button-rounded p-button-info" /> Share


                            <div class="mt-3" >
                                <Textarea v-if="toggleComments" v-model="value1" rows="5" cols="30" placeholder="leave your comment" />
                            </div>
                        </template>
                    </Card>
                </span>
            </div>


            <Button label="Show" icon="pi pi-external-link" @click="toggleAddPostModal" />
                <Dialog header=" NEW POST " :visible.sync="displayAddPostModal" :containerStyle="{width: '50vw'}">
                    <form @submit.prevent="loginUser()">
                    <div class="p-field">
                        <label for="username">Title:</label><br>
                        <InputText type="text" v-model="formData.title" />
                    </div>

                    <div class="p-field">
                        <label for="username">Description:</label><br>
                        <Textarea v-model="formData.description" rows="5" cols="30" placeholder="Description" />
                    </div>
                    
                    </form>
                    <template #footer>
                        <Button label="CANCEL" icon="pi pi-times" @click="toggleAddPostModal" class="p-button-text"/>
                        <Button label="POST" icon="pi pi-check" @click="closeBasic" autofocus />
                    </template>
                </Dialog>

        </template>
    </Default>

  </template>
  
  <script setup>
    import { onMounted, ref } from 'vue';
    import Default from '../../components/Default.vue';
    import InputText from 'primevue/inputtext/InputText';
    import Button from 'primevue/button';
    import Card from 'primevue/card'
    import Textarea from 'primevue/textarea';
    import Dialog from 'primevue/dialog';

    const posts = ref([])
    const searchTerm = ref('')
    const toggleComments = ref(false)
    const displayAddPostModal = ref(false)
const formData = ref(
    {
        title:'',
        description:''
    }
)
    const showComments = ()=>{
        toggleComments.value = true;
    }

    const toggleAddPostModal = ()=>{
        displayAddPostModal.value = !displayAddPostModal.value;
    }
    const getAllPosts = ()=>{
    posts.value= [
        {
            id:1,
            title: "When i was young",
            description: "Yes i was this young",
            tags:"no, 2019, yes",
            images:[
                
            ],
            tags:[
                'wabeb',
                'Ninja',
                'alaah'
            ]
        },

        {
            id:2,
            title: "Wabebe",
            description: "Yes i was this young",
            tags:"no, 2019, yes",
            images:[
                
            ]
        },

        {
            id:3,
            title: "Nikikam through wanajua ni mazishi",
            description: "Yes i was this young",
            tags:"no, 2019, yes",
            images:[
                
            ]
        },

        {
            id:4,
            title: "Yess banaaa  , nimegrow",
            description: "Yes i was this young",
            tags:"no, 2019, yes",
            images:[
                'old.jpeg'
            ]
        }
        
    ]
    }

    onMounted(()=>{
        getAllPosts()
    })

  </script>

  <style>
  .header{
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-between;
  }

  .posts{
    margin:1% 10%;
  }

  .post-card{
    width:100%;
    margin:2%;
  }

</style>