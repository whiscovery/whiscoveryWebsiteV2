s<template>
  <div>
    <v-container>
      <v-col v-for="(item, i) in studys" :key="i" cols="12">
        <v-hover v-slot="{ hover }" open-delay="100">
          <v-card :elevation="hover ? 16 : 2" :class="{ 'on-hover': hover }">
            <div class="d-flex flex-no-wrap justify-space-between">
              <div class="myborder">
                <v-card-title class="study-name"
                  >{{ item.name }}{{ studyId }}
                  <span class="study-name-writer">
                    <v-chip x-small color="deep-purple accent-4" outlined>{{
                      item.writer
                    }}</v-chip></span
                  ></v-card-title
                >
                <v-chip-group column class="study-subcontents">
                  <v-chip x-small>{{ item.category }}</v-chip>
                  <v-chip x-small>{{ item.country }}</v-chip>
                </v-chip-group>

                <v-img
                  :src="item.photo"
                  class="study-photo"
                  max-height="125"
                  contain
                ></v-img>
                <strong>테이스팅 노트</strong>
                <p v-html="item.basic" class="study-contents"></p>

                <strong>설명</strong>
                <p v-html="item.desc" class="study-contents"></p>

                <v-card-actions>
                  <v-spacer></v-spacer>

                  <router-link
                    :to="{
                      name: 'Study',
                      params: {
                        studyId: item.id
                      }
                    }"
                    ><v-btn icon>
                      <v-icon>mdi-unfold-more-vertical</v-icon>
                    </v-btn></router-link
                  >
                  <v-btn icon>
                    <v-icon>mdi-comment-edit</v-icon>
                  </v-btn>

                  <v-btn icon>
                    <v-icon>mdi-delete</v-icon>
                  </v-btn>
                </v-card-actions>
              </div>
            </div>
          </v-card>
        </v-hover>
      </v-col>
    </v-container>
  </div>
</template>
<script>
export default {
  computed: {
    studyId() {
      return this.$route.params.studyId;
    }
  },
  data() {
    return {
      studys: [
        {
          id: 1,
          name: "그란츠 18년",
          writer: "지원찡",
          category: "브렌디드 위스키",
          country: "스카치 위스키",
          basic:
            "향(Nose) : 오렌지껍질필링, 생강과 시나몬 느낌이 가미된 카라멜라이즈<br/>맛(Palate) : 골든시럽, 쥬시한 건포도, 바닐라와 시가 믹스<br />피니쉬(Finish) : 긴 편, 꿀내음",
          photo:
            "https://www.kajawine.kr/data/item/1584243046/thumb-Grants18Year64yA_220x320.jpg",
          desc:
            "18년짜리인데도 금액을 보면 3.9만원으로 매우 저렴합니다.<br />그 이유는 블렌디드에 있는데요, 블렌디드라고 다 저렴하지도 않잖아용?<br />조니워커블루는 블렌디드인데 비싸잖아유.<br /><br />그란츠에 들어간 18년 숙성 원액들 중에는 그레인이 있는데 (아마도 다분히),<br />그레인은 연속식증류를 하기 때문에 많은 성분들이 빠져나가요.<br />그래서 숙성해도 고만고만해요. 게다가 이미 2-3번 사용한 오크통에 숙성을 시키니<br />우러나올 게 별로 없고, 그에 맞춰 기대할 수 있는 가치도 낮으므로<br />18년 숙성 원액을 섞었다고 해도 비싼 값을 받기가 애매한 거죠. (팔리지도 않을것이고요)<br /><br />그래서 무조건 앞에 높은 연수가 쓰여있다고 해서 무조건 고숙성! 좋은 제품은 아닙니다~<br />현 위스키 시장에서는 고숙성은 싱글몰트를 그래도 높게 쳐준다는 거~<br /><br />제 생각으로는 이 사실들을 모르는 소비자들이나, 업장에서 하이볼용이나 칵테일 제조용으로<br />많이 구매해서 1위라는 숫자를 만들어 낸 게 아닌가 싶습니당*_*"
        }
      ]
    };
  }
};
</script>
<style>
body {
  margin: 0;
  padding: 0;
}
.study-card {
  box-shadow: 0 20px 30px 0 rgba(238, 142, 188, 0.3);
  transform: scale(1.05);
}
.study-name {
  background: #000;
  background: -webkit-linear-gradient(left, #0e0e0e, #000);
  background: -moz-linear-gradient(right, #0e0e0e, #000);
  background: -o-linear-gradient(right, #0e0e0e, #000);
  background: linear-gradient(to right, rgb(46, 46, 46), #000);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  padding: 10px 10px 10px 10px;

  margin: 0;
}
.study-name-writer {
  font-size: 10px;
  display: inline-block;
  padding: 10px 10px 0 20px;
}
.study-writer {
  font-family: "Nanum Gothic", sans-serif;
  font-size: 15px;
}
.study-contents {
  font-family: "Nanum Gothic", sans-serif;
  font-size: 12px;
  margin-left: 20px;
}
.study-subcontents {
  font-size: 8px;
  padding: 0px 0px 0px 0px;
  margin: 0 0 0 10px;
}
.study-photo {
  float: left;
  margin-left: 20px;
  margin-right: 20px;
  margin-top: 20px;
  margin-bottom: 20px;
  clear: both;
  width: 100px;
}
.myborder {
  width: 100%;
  border: 3px dashed red;
}
</style>
