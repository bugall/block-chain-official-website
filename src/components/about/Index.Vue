<template>
    <main><!--main Start --> 
			<section class="section-group lis-10 salon-ad">
				<div class="container">
                    <h2 class="f-l c-white" data-aos="zoom-in" data-aos-delay="200"> 关于我们 </h2>
                    <h3 class="f-l c-white" data-aos="zoom-in" data-aos-delay="300"> 我们愿意坦诚介绍自己 </h3>
				</div>
			</section>
			
			<section class="section-group listab-box">
				<div class="container">
          <div class="c-box tab-box slide-tab">
          	<div class="f-l hd bgc-white zh-tabhd-1">
          		<ul class="f-l">
          			<li @click="navTabClick" :class="{on: this.currentTab === 'zuzhijiagou'}" data-type="zuzhijiagou" class="f-l c-gray3"> 组织架构 <em class="f-l em tran-sition transform-scale"></em></li>
          			<li @click="navTabClick" :class="{on: this.currentTab === 'yanjiuyuan'}" data-type="yanjiuyuan" class="f-l c-gray3"> 研究院介绍 <em class="f-l em tran-sition transform-scale"></em></li>
          			<li @click="navTabClick" :class="{on: this.currentTab === 'huiyuanzhangcheng'}" data-type="huiyuanzhangcheng" class="f-l c-gray3"> 会员章程 <em class="f-l em tran-sition transform-scale"></em></li>
          			<li @click="navTabClick" :class="{on: this.currentTab === 'huiyuanshenqing'}" data-type="huiyuanshenqing" class="f-l c-gray3"> 会员申请 <em class="f-l em tran-sition transform-scale"></em></li>
          		</ul>
          	</div>
          	<div class="f-l bd">
                  <v-zuzhijiagou v-if="this.currentTab === 'zuzhijiagou'"></v-zuzhijiagou>
                  <v-yanjiuyuan v-else-if="this.currentTab === 'yanjiuyuan'"></v-yanjiuyuan>
                  <v-huiyuanzhangcheng v-else-if="this.currentTab === 'huiyuanzhangcheng'"></v-huiyuanzhangcheng>
                  <v-huiyuanshenqing v-else-if="this.currentTab === 'huiyuanshenqing'"></v-huiyuanshenqing>
          	</div>
          </div>
				</div>
			</section>		
    </main>
</template>

<script>
    import huiyuanshenqing from './template/Huiyuanshenqing.vue';
    import huiyuanzhanghcheng from './template/Huiyuanzhangcheng.vue';
    import yanjiuyuan from './template/Yanjiuyuan.vue';
    import zuzhijiagou from './template/Zuzhijiagou.vue';

    export default {
        data () {
            return {
                search: '',
                currentTab: 'zuzhijiagou'
            };
        },
        created () {
        },
        mounted () {
            window.AOS.init();
        },
        methods: {
            clearInput () {
                this.setKeywords({keywords: ''});
            },
            navTabClick (element) {
                this.currentTab = element.target.getAttribute('data-type');
            }
        },
        components: {
            vHuiyuanshenqing: huiyuanshenqing,
            vHuiyuanzhangcheng: huiyuanzhanghcheng,
            vYanjiuyuan: yanjiuyuan,
            vZuzhijiagou: zuzhijiagou
        }
    };
</script>

<style scoped>
    .header-wrap {
        width: 100%;
        height: 60px;
        background: rgb(84, 92, 100);
        margin: auto;
        position: fixed;
        z-index: 100;
        top: 0px;
    }
    .header-wrap .el-col {
        height: 100%;
    }
    .header-wrap .brand img {
        width: 70px;
        margin-top: 10px;
    }

    .nav-menu-item-right {
        float: right !important;
    }
    .el-menu-item {
        text-align: center;
    }
    

</style>
<style>
    .popuper {
        margin-left: -20px;
    }
    .popuper .el-menu--popup {
        min-width: 140px !important;
    }
</style>
