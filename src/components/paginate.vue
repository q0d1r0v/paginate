<template>
    <div class="parent">
        <div class="body">
            <div>
                <span class="num">{{ pPage }}
                </span>
                <br>
                <span class="author">by-kadirov</span>
            </div>
        </div>
        <div class="parent-paginate">
            <div class="body-paginate">
                <div class="paginate">
                    <div class="number" v-for="(num, index) of totalVisible" :key="index" @click="changePage(num)">
                        {{ num }}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['page', 'length', 'totalVisible'],
    name: "paginate",

    data() {
        return {
            pPage: 1,
            pLength: 1,
            pTotalVisible: 1,
        }
    },

    mounted() {
    },
    methods: {
        changePage(page) {
            this.pPage = page
        }
    }
};
</script>

<style>
.author {
    color: gray;
    font-size: 12px;
}

.parent {
    width: 100%;
    height: 100vh;
    background: #fff;
}

.body {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
}

.parent-paginate {
    width: 100%;
    height: 70px;
    background: lightgreen;
    box-shadow: 0px 0px 25px 3px lightgreen;
    position: -webkit-sticky;
    position: sticky;
    bottom: 0;
}

.body-paginate {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
}

.paginate {
    min-width: 100px;
    height: 50px;
    background: #fff;
    box-shadow: 0px 0px 10px -2px #fff;
    border-radius: 5px;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 5px;
}

.number {
    min-width: 40px;
    border-radius: 5px;
    height: 40px;
    background: lightgreen;
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.3s;
    cursor: pointer;
    margin: 5px;
    -webkit-user-select: none;
}

.number:hover {
    background: rgb(157, 247, 157);
}

.number:active {
    background: rgb(170, 255, 170);
}

.num {
    font-size: 200px;
    font-weight: bold;
    -webkit-user-select: none;
}
</style>
