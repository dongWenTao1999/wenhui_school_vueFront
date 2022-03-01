<template>
  <div id="aCoursesList" class="bg-fa of">
    <!-- 讲师介绍 开始 -->
    <section class="container">
      <header class="comm-title">
        <h2 class="fl tac">
          <span class="c-333">讲师介绍</span>
        </h2>
      </header>
      <div class="t-infor-wrap">
        <!-- 讲师基本信息 -->
        <section class="fl t-infor-box c-desc-content">
          <div class="mt20 ml20">
            <section class="t-infor-pic">
              <img :src="teacher.avatar" />
            </section>
            <h3 class="hLh30">
              <span class="fsize24 c-333"
                >{{ teacher.name }}&nbsp;
                {{ teacher.level === 1 ? "高级讲师" : "首席讲师" }}
              </span>
            </h3>
            <section class="mt10">
              <span class="t-tag-bg">{{ teacher.intro }}</span>
            </section>
            <section class="t-infor-txt">
              <p class="mt20">{{ teacher.career }}</p>
            </section>
            <div class="clear"></div>
          </div>
        </section>
        <div class="clear"></div>
      </div>
      <section class="mt30">
        <div>
          <header class="comm-title all-teacher-title c-course-content">
            <h2 class="fl tac">
              <span class="c-333">主讲课程</span>
            </h2>
            <section class="c-tab-title">
              <a href="javascript: void(0)">&nbsp;</a>
            </section>
          </header>
          <!-- /无数据提示 开始-->
          <section class="no-data-wrap" v-if="courseList.length == 0">
            <em class="icon30 no-data-ico">&nbsp;</em>
            <span class="c-666 fsize14 ml10 vam"
              >没有相关数据，小编正在努力整理中...</span
            >
          </section>
          <!-- /无数据提示 结束-->
          <article class="comm-course-list">
            <ul class="of">
              <li v-for="course in courseList" :key="course.id">
                <div class="cc-l-wrap">
                  <section class="course-img">
                    <img :src="course.cover" class="img-responsive" />
                    <div class="cc-mask">
                      <a
                        :href="url"
                        title="开始学习"
                        class="comm-btn c-btn-1"
                        @>开始学习</a
                      >
                    </div>
                  </section>
                  <h3 class="hLh30 txtOf mt10">
                    <a
                      :href="url"
                      :title="course.title"
                      class="course-title fsize18 c-333"
                      
                      >{{ course.title }}</a
                    >
                  </h3>
                </div>
              </li>
            </ul>
            <div class="clear"></div>
          </article>
        </div>
      </section>
    </section>
    <!-- /讲师介绍 结束 -->
  </div>
</template>
<script>
export default {
  //params.id获取路径id值
  data() {
    return {
      teacher: {
        level: 2,
        name: "老师1",
        avatar: require("../../assets/photo/teacher/06.jpg"),
        career: "教授",
        intro:
          "资深项目经理、技术讲师、SUN SCJP、SCWCD、原工信部移动云计算教育培训中心教学总监。 十年软件开发经验：参与完成辽宁某高校远程教学管理系统、慧文信息门户系统、日本麦卡尔超市管理系统、崎玉市外来人口登记系统、深海视频会议管理系统、仙台市宫城县日常事务系统等项目的设计和开发。 十年软件培训经验：曾在中国AOP全球外包排名第一的公司任Java、Oracle培训讲师、负责对公司员工新技术培训；曾任花旗银行特约JavaEE培训讲师；某部队研究所JavaEE培训；曾受聘为北航、厦门大学移动云计算专业教学主任， 并主讲Java、Android、iOS课程。",
      },
      courseList:[
        {
          id: 1,
          title: "课程1",
          buyCount: 100,
          viewCount: 200,
          price: 50,
          cover: require("../../assets/photo/course/05.jpg"),
        },
                {
          id: 2,
          title: "课程2",
          buyCount: 100,
          viewCount: 200,
          price: 50,
          cover: require("../../assets/photo/course/05.jpg"),
        },
                {
          id: 3,
          title: "课程3",
          buyCount: 100,
          viewCount: 200,
          price: 50,
          cover: require("../../assets/photo/course/05.jpg"),
        },
                {
          id: 4,
          title: "课程4",
          buyCount: 100,
          viewCount: 200,
          price: 50,
          cover: require("../../assets/photo/course/05.jpg"),
        },
      ],
      url:"/course/2"
    };
  },
  methods:{
  }
};
</script>