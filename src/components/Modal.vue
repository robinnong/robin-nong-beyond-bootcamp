<template>
    <div class="modalOuter" @click=closeModal>
        <div class="modalInner">
            <h3>{{ result.message }}</h3> 
            <p class="grade">{{ result.grade }}</p>
            <p>{{ finalScore }} of 30 matches correct</p>
            <button @click=closeModal id="modalButton">Exit</button>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Modal',  
        props: ['finalScore', 'result'],
        methods: {
            closeModal(e) {
                this.$emit('close-modal', e)
            }, 
        }
    }  
</script>

<style lang="scss" scoped>
    .modalOuter {
        position: fixed;
        top: 0;
        right: 0;
        left: 0;
        bottom: 0;
        z-index: 10; 

        display: flex;
        background-color: #0000003a;
        opacity: 1;
        pointer-events: all; 
        transition: all 0.2s; 
        div {   
            width: 300px;  
            padding: 30px 20px;
            margin: auto;
            background-color: white;
            border: 1px solid #d4d4d4;
            border-radius: 5px;
            box-shadow: 0 0 5px 5px #24242407;  

            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center; 
        }  
        button {  
            color: white;
            margin-top: 15px;
            padding: 10px 30px;
            background-color: #ff85aa;  
            box-shadow: 0 0 10px 2px #e77a9b5d;
            border-radius: 5px;
            transition: all 0.2s;
            cursor: pointer;
                &:focus,
                &:hover {background-color: #e77a9b;}
        } 
    } 

    .grade {
        font-size: 2.8rem;
        font-weight: 600;
        color: #e77a9b;
        margin: 10px 0;
    } 
</style>