s<template>
  <div>
    <v-container>
      <v-col v-for="(item, i) in studys" :key="i" cols="12">
        <v-hover v-slot="{ hover }" open-delay="100">
          <v-card :elevation="hover ? 16 : 2" :class="{ 'on-hover': hover }">
            <div class="d-flex flex-no-wrap justify-space-between">
              <div class="myborder">
                <v-card-title class="study-name"
                  >{{ item.name }}
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

                <v-card-actions>
                  <v-avatar class="ma-3" size="125" tile>
                    <v-img :src="item.photo"></v-img>
                  </v-avatar>
                  <v-card-text>
                    <p v-html="item.basic" class="study-contents"></p>
                  </v-card-text>
                </v-card-actions>
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
            "https://www.kajawine.kr/data/item/1584243046/thumb-Grants18Year64yA_220x320.jpg"
        },
        {
          id: 2,
          name: "발베니 더블우드 12년",
          writer: "호동",
          category: "싱글몰트 위스키",
          country: "스카치 위스키",
          basic:
            "향은 달콤한 과일, 올로로소 셰리, 꿀, 바닐라 향이 겹쳐져 느껴집니다.<br />맛(Palate): 견과의 단맛, 시나몬 스파이스와 우아한 균형의 셰리가 훌륭한 조합을 이루며 부드럽고 달콤한 풍미를 제공합니다.<br />피니쉬(Finish): 따뜻한 오랜 여운을 남깁니다.",
          photo:
            "https://www.kajawine.kr/data/item/1329702671/thumb-1329702671_l1_220x320.jpg"
        },
        {
          id: 3,
          name: "그란츠 18년",
          writer: "지원찡",
          category: "브렌디드 위스키",
          country: "스카치 위스키",
          basic:
            "향(Nose) : 오렌지껍질필링, 생강과 시나몬 느낌이 가미된 카라멜라이즈<br/>맛(Palate) : 골든시럽, 쥬시한 건포도, 바닐라와 시가 믹스<br />피니쉬(Finish) : 긴 편, 꿀내음",
          photo: "https://cdn.vuetifyjs.com/images/cards/foster.jpg"
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
}
.study-subcontents {
  font-size: 8px;
  padding: 0px 0px 0px 0px;
  margin: 0 0 0 10px;
}
.myborder {
  width: 100%;
  border: 3px dashed red;
}
</style>
