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
                    <div class="lNumber" @click="goFirst()">
                        <img src="../assets/two-left-arrow.png" width="20px" />
                    </div>
                    <div class="lNumber" @click="leftPage()">
                        <img src="../assets/left-arrow.png" width="20px" />
                    </div>
                    <div class="pNumber">
                        {{ pPage }}
                    </div>
                    <div class="rNumber" @click="rightPage()">
                        <img src="../assets/right-arrow.png" width="20px" />
                    </div>
                    <div class="rNumber" @click="goEnd()">
                        <img src="../assets/two-right-arrow.png" width="20px" />
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['page', 'length',],
    name: "paginate",

    data() {
        return {
            pPage: this.page,
        }
    },

    watch: {
        pPage() {
            this.updatePage()
        }
    },

    mounted() {
    },
    methods: {
        rightPage() {
            if (this.pPage < this.length) {
                this.pPage++
                document.getElementsByClassName("lNumber")[0].style.setProperty('background-color', 'lightgreen', 'important')
                document.getElementsByClassName("lNumber")[1].style.setProperty('background-color', 'lightgreen', 'important')
            } else if (this.pPage === this.length) {
                document.getElementsByClassName("rNumber")[0].style.setProperty('background-color', 'rgba(155, 155, 155, 0.445)', 'important')
                document.getElementsByClassName("rNumber")[1].style.setProperty('background-color', 'rgba(155, 155, 155, 0.445)', 'important')
            }
        },
        leftPage() {
            if (this.pPage <= this.length && this.pPage !== 1) {
                this.pPage--
                document.getElementsByClassName("rNumber")[0].style.setProperty('background-color', 'lightgreen', 'important')
                document.getElementsByClassName("rNumber")[1].style.setProperty('background-color', 'lightgreen', 'important')
            } else if (this.page === 1) {
                document.getElementsByClassName("lNumber")[0].style.setProperty('background-color', 'rgba(155, 155, 155, 0.445)', 'important')
                document.getElementsByClassName("lNumber")[1].style.setProperty('background-color', 'rgba(155, 155, 155, 0.445)', 'important')
            }
        },
        goEnd() {
            this.pPage = this.length
            document.getElementsByClassName("rNumber")[1].style.setProperty('background-color', 'rgba(155, 155, 155, 0.445)', 'important')
            document.getElementsByClassName("rNumber")[0].style.setProperty('background-color', 'rgba(155, 155, 155, 0.445)', 'important')

            document.getElementsByClassName("lNumber")[0].style.setProperty('background-color', 'lightgreen', 'important')
            document.getElementsByClassName("lNumber")[1].style.setProperty('background-color', 'lightgreen', 'important')
        },
        goFirst() {
            this.pPage = 1
            document.getElementsByClassName("lNumber")[0].style.setProperty('background-color', 'rgba(155, 155, 155, 0.445)', 'important')
            document.getElementsByClassName("lNumber")[1].style.setProperty('background-color', 'rgba(155, 155, 155, 0.445)', 'important')

            document.getElementsByClassName("rNumber")[0].style.setProperty('background-color', 'lightgreen', 'important')
            document.getElementsByClassName("rNumber")[1].style.setProperty('background-color', 'lightgreen', 'important')
        },
        updatePage() {
            this.$emit("updatePage", this.pPage)
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

.pNumber {
    min-width: 50px;
    border-radius: 5px;
    font-size: 20px;
    height: 50px;
    background: lightgreen;
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.3s;
    margin: 5px;
    -webkit-user-select: none;
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

.lNumber {
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

.lNumber:hover {
    background: rgb(157, 247, 157);
}

.rNumber {
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

.rNumber:hover {
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