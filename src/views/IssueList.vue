<template>
    <div>
        <h1>List</h1>
            <el-button type="success" @click="getIssues()">issue取得</el-button>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    name: 'IssueList',
    data(){
        return {
            issues:[]
        }
    },
    methods: {
        getIssues(){
            axios.get('https://api.github.com/repos/yohayako/todo-app-project',
                {
                    headers:{
                        'Accept': 'application/vnd.github.v3+json',
                        'Content-Type':'application/json',
                        },
                },
            )
            .then((res)=>{
                this.issues =res
            })
        }
    }
}
</script>

