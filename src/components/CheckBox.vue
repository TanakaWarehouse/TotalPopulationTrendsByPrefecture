<script>
//axiosの使用はAPIからデータを取得して表示することに対しての一般的アプローチ
import axios from 'axios'

export default{
    mounted(){
        //JavaScriptではconstでも中身変化することあり→大文字使わないほうがよさそう．
        const prefectures_url = 'https://opendata.resas-portal.go.jp/api/v1/prefectures';
        axios.get(prefectures_url,{headers: {'X-API-KEY': '8VMwXkVSFZEWRwjiYIHdOa5FlYkgrXTq1YXkBnO6'}})
        .then(response => console.log(response));
    }
}
</script>

<template></template>