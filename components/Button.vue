<template>
    <button class="btn">{{text}}</button>
</template>

<script>
export default {
    props: {
        text: String,
    }
}
</script>

<style>
.btn {
    cursor: pointer;
    padding:10px;
    background:green;
    border-radius: 5px;
    transition: 0.25s;
    margin: 0 5px;
    border:none;
    color:white;
    font-size: 16px;
    font-weight: bold;
    transition: 0.25s;
    margin: 0 25px;
    filter:drop-shadow(0px 0px 3px gray);
} 

.btn:hover {
    background: orange;
    padding:9px;
}
   </style>