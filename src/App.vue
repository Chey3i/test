<template>       
    <div :class="[theme ? 'black-theme' : 'white-theme', 'block']" >
        <div :class="[theme ? 'black-theme' : 'white-theme', 'block-1']">
            <div class="data-time-exit">
                <div class="data-time">
                    <div>{{dataUser}}</div>
                    <div>{{timeUser}}</div> 
                </div>
                <div class="exit">
                    <div>Выход</div>
                    <img :class="[theme ? 'img-exit-white' : 'img-exit-black']" src=".\exitIcon.png" alt="exit">
                </div>
            </div>
            <div class="toggle-component">
                <input @click="myFilter" type="checkbox" id="toggle_checkbox">
                <label for="toggle_checkbox">
                    <div id="star">
                        <div class="star" id="star-1">★</div>
                        <div class="star" id="star-2">★</div>
                    </div>
                    <div id="moon"></div>
                </label>
            </div>
            <div class="card">

                <div class="fio">{{fio}}</div>
                <div class="date-of-birth">{{date-of-birth}}</div>
                <div class="tabN">Таб №: {{tabN}}</div>
                <div class="position">{{position}}</div>
            
            </div>
            <div class="information-for-users">
                <div class="info-box" v-for="userINFO in UserInformations" v-bind:key="userINFO">
                    <div>{{userINFO.title}}</div>
                    <div><img class="img-1" :src="userINFO.img" alt="1"></div>
                </div>
            </div>  
        </div>
        <div class="block-2">
            <div class="block-3">
                <div class="move-box" v-for="moveINFO in moveInformations" v-bind:key="moveINFO">
                    <div>{{moveINFO.title}}</div>
                    <div><img class="img-2" :src="moveINFO.img" alt="1"></div>   
                </div> 
            </div>
            <div class="logo">
                <img class="logo-img" src="./logo.png" alt="logo">
            </div>
        </div>
    </div>       
</template>

<script>
export default {
    data() {
        return {
            dataUser : 'XX.XX.XXXX',
            timeUser : 'XX.XX',
            theme: true,
            fio: 'Фамилия Имя Отчество',
            dateofBirth: 'XX.XX.XXXX',
            tabN: 'ГОКИ 0000',
            position: 'Проходчик IV разряда',
            UserInformations:[
                {id:1, title:'Инструктаж', img: ''},
                {id:2, title:'Предсменный экзаменатор', img: ''},
                {id:3, title:'Тестов выполнено', img: ''},
                {id:4, title:'Аттестация через', img: ''},
            ],
            moveInformations:[
                {id:1, title:'Начать работу', img: ''},
                {id:2, title:'Уведомления', img: ''},
                {id:3, title:'Обучение', img: ''},
                {id:4, title:'Достижения', img: ''},
            ],
           
        }
    },
    methods: {
        myFilter: function() {this.theme = !this.theme;},}
}
</script>

