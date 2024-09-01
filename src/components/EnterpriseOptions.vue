<template>
    <div class="EnterpriseOptions">
        <div class="EnterpriseOptions__action">
            <div class="EnterpriseOptions__action-img">
                <transition name="imageset">
                    <img :src="imageUrl" alt="" id="image" :class="{ 'blur': isBlurred }">
                </transition>
                <div class="Maskcontent">
                </div>
            </div>
            <div class="EnterpriseOptions__title">
                <p>全行业定制化配送解决方案 服务无忧 体验更优</p>
                <span>超过2000000+来自不同行业的商家选择使用UU跑腿</span>
            </div>
        </div>
        <div class="EnterpriseOptions__content">
            <ul>
                <template v-for="(item, index ) in options " :key="item.id">
                    <li @mouseenter="toggleBox(index)" class="colorset">
                        <img :src="item.img" alt="">
                        <span>{{ item.title }}</span>
                    </li>
                </template>

            </ul>
            <transition name="EnterActionset">
                <div class="EnterpriseOptions__content-butom" :class="{ 'move-up': isBoxVisible }"></div>
            </transition>
        </div>
    </div>
</template>
<script>
// 动画 animate.css


export default {
    name: 'EnterpriseOptions',

    data() {
        return {
            options: [
                {
                    id: 1,
                    title: '外卖餐饮配送',
                    img: require('../../public/icon_sbise1yjovh/24gf-bag.png')
                },
                {
                    id: 2,
                    title: '鲜花配送',
                    img: require('../../public/icon_sbise1yjovh/chufadihedidian.png')
                },
                {
                    id: 3,
                    title: '3c数码配送',
                    img: require('../../public/icon_sbise1yjovh/dangao.png')
                },
                {
                    id: 4,
                    title: '蛋糕配送',
                    img: require('../../public/icon_sbise1yjovh/tel.png')
                }

            ],
            images: [
                require('../assets/image/set.png'),
                require('../assets/image/one.jpg'),
                require('../assets/image/forw.png'),
                require('../assets/image/three.png')
            ],
            imageUrl: require('../assets/image/set.png'),
            isBoxVisible: false,
            isAnimating: false,
            isBlurred: false,
            preloadedImages: []
        }
    },
    mounted() {
        this.preloadImages();
    },
    methods: {
        preloadImages() {
            this.images.forEach((image) => {
                const img = new Image();
                img.src = image;
                img.onload = () => {
                    this.preloadedImages.push(image)
                };
            });
        },
        toggleBox(index) {
            this.isBlurred = true;
            setTimeout(() => {
                this.imageUrl = this.preloadedImages[index];


                // 移除模糊效果
                this.isBlurred = false;
            }, 300);


            // // 设置新的图片源  
            // this.imageUrl = this.images[index];

            // // 可选：立即应用模糊效果，然后通过 setTimeout 移除以实现过渡  
            // // 这里我们直接在下一帧移除模糊效果，以实现快速的从模糊到清晰的过渡  
            // this.$nextTick(() => {
            //     image.classList.add('blur');
            //     setTimeout(() => {
            //         image.classList.remove('blur');
            //     }, 50); // 50 毫秒后移除模糊效果，你可以根据需要调整这个时间  
            // });


            // var image = document.getElementById('myImage');
            // image.classList.toggle('blur');
            // this.imageUrl = this.images[index]
            // // 这个还行
            // var image = document.getElementById('myImage');
            // image.style.filter = 'blur(0px)';
            if (this.isAnimating) return;  //如果正在动画中，直接返回
            this.isAnimating = true;
            this.isBoxVisible = true;
            setTimeout(() => {
                this.isBoxVisible = false;
                setTimeout(() => {
                    this.isAnimating = false;  //动画结束后重置 isAnimating
                }, 200);  //等待动画结束后重置 isAnimating
            }, 200);  //只保留上移的动画效果






            // if (id == 1) {
            //     this.imageUrl = this.images[0]
            //     this.isBoxVisible = true
            //     if (this.isAnimating) return; // 如果正在动画中，直接返回
            //     this.isAnimating = true;
            //     this.isBoxVisible = true;
            //     setTimeout(() => {
            //         this.isBoxVisible = false;
            //         setTimeout(() => {
            //             this.isAnimating = false; // 动画结束后重置 isAnimating
            //         }, 200); // 等待动画结束后重置 isAnimating
            //     }, 200);
            // }
            // if (id == 2) {
            //     this.isBoxVisible = true
            //     this.imageUrl = this.images[1]
            //     if (this.isAnimating) return; // 如果正在动画中，直接返回
            //     this.isAnimating = true;
            //     this.isBoxVisible = true;
            //     setTimeout(() => {
            //         this.isBoxVisible = false;
            //         setTimeout(() => {
            //             this.isAnimating = false; // 动画结束后重置 isAnimating
            //         }, 200); // 等待动画结束后重置 isAnimating
            //     }, 200);

            // }
            // if (id == 3) {
            //     this.isBoxVisible = true

            //     this.imageUrl = this.images[2]
            //     if (this.isAnimating) return; // 如果正在动画中，直接返回
            //     this.isAnimating = true;
            //     this.isBoxVisible = true;
            //     setTimeout(() => {
            //         this.isBoxVisible = false;
            //         setTimeout(() => {
            //             this.isAnimating = false; // 动画结束后重置 isAnimating
            //         }, 200); // 等待动画结束后重置 isAnimating
            //     }, 200);

            // }
            // if (id == 4) {
            //     this.isBoxVisible = true

            //     this.imageUrl = this.images[3]
            //     if (this.isAnimating) return; // 如果正在动画中，直接返回
            //     this.isAnimating = true;
            //     this.isBoxVisible = true;
            //     setTimeout(() => {
            //         this.isBoxVisible = false;
            //         setTimeout(() => {
            //             this.isAnimating = false; // 动画结束后重置 isAnimating
            //         }, 200); // 等待动画结束后重置 isAnimating
            //     }, 200);

            // }

            // 只保留上移的动画效果
        }

        // toggleBox() {
        //     if (this.isAnimating) return; // 如果正在动画中，直接返回
        //     this.isAnimating = true;
        //     this.isBoxVisible = true;
        //     setTimeout(() => {
        //         this.isBoxVisible = false;
        //         setTimeout(() => {
        //             this.isAnimating = false; // 动画结束后重置 isAnimating
        //         }, 300); // 等待动画结束后重置 isAnimating
        //     }, 300); // 只保留上移的动画效果
        // }
    },

}
</script>
<style scoped lang="scss">
.EnterpriseOptions {
    width: 100%;
    height: 800px;
    margin-top: 150px;
    position: relative;
    overflow: hidden;

    .EnterpriseOptions__action {
        height: 50%;
        width: 100%;
        position: relative;

        .EnterpriseOptions__action-img {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;

            .Maskcontent {
                width: 100%;
                height: 100%;
                position: absolute;
                top: 0;
                left: 0;
                background-color: rgba(0, 0, 0, 0.7);
            }
        }


        .EnterpriseOptions__title {
            position: absolute;
            left: 50%;
            top: 25%;
            text-align: center;
            transform: translate(-50%, -50%);
            color: white;
        }

        .EnterpriseOptions__title>p {
            font-size: 35px;
            font-weight: 900;
            margin-bottom: 10px;
        }

        .EnterpriseOptions__title>span {
            font-size: 18px;
            color: #9eaaae;

        }
    }

    .EnterpriseOptions__content {
        width: 60%;
        height: 100%;
        position: absolute;
        top: -28%;
        left: 50%;
        transform: translateX(-50%);
        bottom: 280px;
        position: relative;
        animation: none;

        /* 初始时不播放动画 */
        ul {
            width: 100%;
            height: 100px;
            display: flex;
            justify-content: space-around;

            li {
                width: 25%;
                height: 100%;
                border: 1px solid white;
                display: flex;
                align-items: center;
                justify-content: center;
                box-sizing: border-box;
                -moz-box-sizing: border-box;
                -webkit-box-sizing: border-box;

                img {
                    width: 30px;
                    height: 25px;
                    padding-right: 5px;
                }

                span {
                    font-size: 20px;
                    color: white;
                    font-weight: 700;
                }
            }

            li:hover {
                background-color: #ff6900;
                border: none;
            }

            li:hover span {
                transform: scale(1.2);
                margin-left: 10px;
            }

            li:hover img {
                transform: scale(1.2);
            }

            li:nth-child(1) {
                border-right: none;
            }

            li:nth-child(2) {
                border-right: none;
            }

            li:nth-child(3) {
                border-right: none;
            }
        }

        .EnterpriseOptions__content-butom {
            transition: transform 0.5s;
            margin-top: 30px;
            width: 100%;
            height: 100%;
            background-color: #ff6900;
        }

    }
}

// 图片的动画效果
#image {
    width: 100%;
    height: auto;
    transition: filter 0.3s;
    height: 100%;
}

.blur {
    filter: blur(10px);
}

.imageset-blur-enter-active,
.imageset-blur-leave-active {
    transition: opacity 0.3s, filter 0.3s;
}

.imageset-blur-enter,
.imageset-blur-leave-to

/* .imageset-blur-leave-active 在 <2.1.8 版本中 */
    {
    opacity: 0;
    filter: blur(0px);
    /* 可以在离开时移除模糊效果，但在这个场景下可能不需要 */
}

// @keyframes fade-in {
//     from {
//         opacity: 0.2;
//     }

//     to {
//         opacity: 1;
//     }
// }

// .fade-enter-active,
// .fade-leave-active {
//     transition: opacity 0.5s;
// }

// .fade-enter,
// .fade-leave-to {
//     opacity: 0;
// }

.ment {
    animation: fade-in 0.5s;
}

// 盒子的动画
.EnterActionset-enter-active,
.EnterActionset-leave-active {
    transition: opacity 0.1s;
}

.EnterActionset-enter,
.EnterActionset-leave-to {
    opacity: 0;
}

.move-up {
    transform: translateY(200px);
    transition: transform 0.1s, opacity 0.3s;
    /* 添加透明度过渡效果 */
    opacity: 1
}
</style>