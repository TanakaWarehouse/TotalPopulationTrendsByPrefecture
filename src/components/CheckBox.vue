<script>
//axiosの使用はAPIからデータを取得して表示することに対しての一般的アプローチ
import axios from 'axios'

export default{
    //data () メソッド内でオブジェクトを定義．returnすることでデータの保持をして、vueのcomponentで必要なときにデータを引っ張ってきて使うことができる。
    data(){
        return{
            prefectures: []
        }
    },
    mounted(){
        //JavaScriptではconstでも中身変化することあり→大文字使わないほうがよさそう．
        const prefectures_url = 'https://opendata.resas-portal.go.jp/api/v1/prefectures';
        axios.get(prefectures_url,{headers: {'X-API-KEY': '8VMwXkVSFZEWRwjiYIHdOa5FlYkgrXTq1YXkBnO6'}})
        
        //response.dataに実際のデータが入っている
        .then(response => this.prefectures = response.data.result);
    }
}
</script>

<template>
    <div class="prefectures-checkbox">
        <label>都道府県一覧</label>
        <li v-for="(prefecture, i) in prefectures">
            <input
                type="checkbox"
                :value="prefecture"
                v-model="selectedPrefectures"
            >
            <!-- v-forを回す回数指定 -->
            <span>{{ prefecture.prefName }}</span>
        </li>
    </div>
</template>