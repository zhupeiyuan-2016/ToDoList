<template>
    <div class= "root">    
    <Form ref="formValidate" :model="formValidate" :rules="ruleValidate" :label-width="40">
        <FormItem label="事件" prop="thing">
            <Input v-model="formValidate.thing" placeholder="Enter your thing"></Input>
        </FormItem>
        <FormItem label="分类" prop="category">
            <Select v-model="formValidate.category" placeholder="Select your category">
                <Option value="beijing">作业</Option>
                <Option value="shanghai">课外</Option>
                <Option value="shenzhen">其他</Option>
            </Select>
        </FormItem>
        <FormItem label="时间">
            <Row>
                <Col span="11">
                    <FormItem prop="date">
                        <DatePicker type="date" placeholder="Select date" v-model="formValidate.date"></DatePicker>
                    </FormItem>
                </Col>
                <Col span="2" style="text-align: center">-</Col>
                <Col span="11">
                    <FormItem prop="time">
                        <TimePicker type="time" placeholder="Select time" v-model="formValidate.time"></TimePicker>
                    </FormItem>
                </Col>
            </Row>
        </FormItem>
        <FormItem label="更多" prop="more">
            <Input v-model="formValidate.more" type="textarea" :autosize="{minRows: 2,maxRows: 5}" placeholder="Enter something..."></Input>
        </FormItem>
        <FormItem>
            <Button type="primary" @click="handleSubmit('formValidate')">Submit</Button>
            <Button @click="handleReset('formValidate')" style="margin-left: 8px">Reset</Button>
        </FormItem>
    </Form>
    </div>
</template>
<script>
    export default {
        data () {
            return {
                formValidate: {
                    thing:'',
                    date:'',
                    time:'',
                    category:'',
                    more:''
                },
                ruleValidate: {
                    thing: [
                        { required: true, message: 'The name cannot be empty', trigger: 'blur' }
                    ],
            }
        }
        },
        methods: {
            handleSubmit (name) {
                this.$refs[name].validate((valid) => {
                    if (valid) {
                        this.$Message.success('Success!');
                    } else {
                        this.$Message.error('Fail!');
                    }
                })
            },
            handleReset (name) {
                this.$refs[name].resetFields();
            }
        }
    }
</script>
<style scoped>
.root{
    height:40vh;
    margin:2rem;
    box-shadow: 3px 3px 3px;
}
</style>
