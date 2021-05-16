<template>
    <form @submit="onSubmit">
        <div class="form-control">
            <label for="text"></label>
            <input type="text" v-model="text" name="text" placeholder="Add Task">
        </div>
        <div class="form-control">
            <label>Day & Time</label>
            <input type="text" v-model="day" name="day" placeholder="Add Day & Time" />
        </div>
        <div class="form-control form-control-check">
            <label>Set Reminder</label>
            <input type="checkbox" v-model="reminder" name="reminder" />
        </div>
        <input type="submit" value="Save Task" class="btn btn-block" />
    </form>
</template>


<script>
    export default {
        name:'AddTask',
        data(){
            return {
                text:'',
                day:'',
                reminder:false
            }
        },
        methods:{
            onSubmit(e){
                e.preventDefault()
                this.$emit('add-task',{
                    id:Math.floor(Math.random()*100000),
                    text:this.text,
                    day:this.day,
                    reminder:this.reminder
                })
            }
        }
    }
</script>
