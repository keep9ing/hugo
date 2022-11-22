---
title: "Two"
date: 2022-11-19T22:31:38+09:00
draft: false
---


** v-for 로 간결하게 만들기 **

<v-card outlined flat min-height="124"
  v-for="(item, i) in indicator" :key="`indicator_${i}`"
  :class="['card rounded-lg', {'ba-blue-ess' : item.checked === true}, {'wide' : item.index > 4}]"
>
  <v-card-title class="justify-start pa-3">
    <v-checkbox hide-details
      v-model="item.checked"
      :ripple="false"
      on-icon="icon-hw_chk-on f20"
      off-icon="icon-hw_chk-off f20"
      class="f13 ma-0 pa-0"
    ></v-checkbox>
    <h3 class="tit f16">{{item.title}}</h3>
  </v-card-title>
  <v-card-text class="px-3 mb-3">
    <v-img
      :src="require(`@/assets/images/${item.img}`)"
      :aspect-ratio="item.ratio"
      contain
      alt=""
      class="pa-3"
    ></v-img>
  </v-card-text>
</v-card>

<script>
export default {
  data() {
    return {
      // 선택지표
      indicator: [
        { index: 1, checked: false, title: '평균 연봉 인상률', img: 'dashboard-chart-1.png', ratio: 3.3857 },
        { index: 2, checked: false, title: '평균 근속년수', img: 'dashboard-chart-2.png', ratio: 3.3857 },
        { index: 3, checked: false, title: '성과급 지급률', img: 'dashboard-chart-3.png', ratio: 3.3857 },
        { index: 4, checked: false, title: '근속기간별 퇴사율', img: 'dashboard-chart-4.png', ratio: 3.3857 },
        { index: 5, checked: false, title: '휴가 사용현황', img: 'dashboard-chart-5.png', ratio: 6.4358 },
        { index: 6, checked: false, title: '평균 근무시간', img: 'dashboard-chart-6.png', ratio: 6.4358 },
      ],
    };
  },
};
</script>
