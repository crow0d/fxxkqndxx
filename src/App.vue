<template>
  <div id="peopleset">
    <div class="people_rank">
      <div class="set_name">
        <div class="set_img">
          <span>
            <img
              src="https://thirdwx.qlogo.cn/mmopen/vi_32/9JvNIibQBKTwrxGJDeTs63rdNSf90DDKaFOj0KbALgBzepNMqFibJRcHk9sye4NVribpicWpklvaGHpaxg55gdMz7Q/132"
            />
          </span>
        </div>
        <div>且听风吟</div>
      </div>
      <div class="set_sign">
        <button class="sing_btn">去签到</button>
      </div>
    </div>
    <div class="study_history h_history">
      <div class="s_history">
        <div class="fl h_img">
          <img src="../public/img/integral.png" />
        </div>
        <div class="s_con">
          <p class="s_stydy">学习记录</p>
          <p class="number">
            <b>31</b>
            次
          </p>
        </div>
      </div>
    </div>
    <div class="s_list">
      <div class="van-tabs van-tabs--line">
        <div class="van-tabs__wrap van-hairline--top-bottom">
          <div role="tablist" class="van-tabs__nav van-tabs__nav--line">
            <div
              role="tab"
              aria-selected="true"
              class="van-tab van-tab--active"
            >
              <span class="van-tab__text van-tab__text--ellipsis">
                网上主题团课
              </span>
            </div>
            <div role="tab" class="van-tab">
              <span class="van-tab__text van-tab__text--ellipsis">
                示范团课
              </span>
            </div>
            <div
              class="van-tabs__line"
              style="
                width: 98.5px;
                transform: translateX(98.5px) translateX(-50%);
              "
            ></div>
          </div>
        </div>
      </div>
      <div class="van-pull-refresh">
        <div class="van-pull-refresh__track" style="transition-duration: 0ms">
          <div role="feed" class="van-list">
            
            <li
              class="synth_list"
              v-for="item in list"
              :key="item"
              :title="item"
            >
              <div class="s3">{{ item.title }}</div>
              <div class="s4">{{ item.time }}</div>
            </li>
          </div>
        </div>
      </div>
    </div>
    <ul class="footer">
      <button class="back">返回</button>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      list: null,
    }
  },
  mounted() {
    axios
      .get('https://api.skyil.cn/qndxx')
      .then((response) => (this.list = response.data,console.log( response.data)))
      .catch(function (error) {
        // 请求失败处理
        console.log(error)
      })
  }
}
</script>
