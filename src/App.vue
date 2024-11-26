<template>
  <div class="car-recommendation">
    <h1>电车还是油车？
    </h1>
    <div class="subtitle">
      <p>购车推荐系统</p>
      <a href="https://x.com/lvwzhen">@lvwzhen</a>
    </div>
      <el-form :model="form">
        <!-- 1. 年行驶公里数 -->
      <div class="form-section">
        <h2>年行驶公里数</h2>
        <div class="options-grid">
          <div class="option-card" 
               :class="{ active: form.mileage === 0 }"
               @click="form.mileage = 0">
            <div class="option-content">
              <div class="option-title">小于 1 万公里</div>
              <div class="option-score">0 分</div>
            </div>
          </div>
          <div class="option-card" 
               :class="{ active: form.mileage === 1 }"
               @click="form.mileage = 1">
            <div class="option-content">
              <div class="option-title">1 万 -2 万公里</div>
              <div class="option-score">1 分</div>
            </div>
          </div>
          <div class="option-card" 
               :class="{ active: form.mileage === 2 }"
               @click="form.mileage = 2">
            <div class="option-content">
              <div class="option-title">2 万 -3 万公里</div>
              <div class="option-score">2 分</div>
            </div>
          </div>
          <div class="option-card" 
               :class="{ active: form.mileage === 3 }"
               @click="form.mileage = 3">
            <div class="option-content">
              <div class="option-title">3 万 + 公里</div>
              <div class="option-score">3 分</div>
            </div>
          </div>
        </div>
      </div>

      <!-- 2. 充电条件 -->
      <div class="form-section">
        <h2>充电条件</h2>
        <div class="options-grid">
          <div class="option-card" 
               :class="{ active: form.charging === 0 }"
               @click="form.charging = 0">
            <div class="option-content">
              <div class="option-title">家里不能装充电桩</div>
              <div class="option-score">0 分</div>
            </div>
          </div>
          <div class="option-card" 
               :class="{ active: form.charging === 1 }"
               @click="form.charging = 1">
            <div class="option-content">
              <div class="option-title">通勤地点有公共桩</div>
              <div class="option-score">1 分</div>
            </div>
          </div>
          <div class="option-card" 
               :class="{ active: form.charging === 2 }"
               @click="form.charging = 2">
            <div class="option-content">
              <div class="option-title">家里能装充电桩</div>
              <div class="option-score">2 分</div>
            </div>
          </div>
          <div class="option-card" 
               :class="{ active: form.charging === 3 }"
               @click="form.charging = 3">
            <div class="option-content">
              <div class="option-title">公司充电桩免费</div>
              <div class="option-score">3 分</div>
            </div>
          </div>
        </div>
      </div>

      <!-- 3. 用车场景 -->
      <div class="form-section">
        <h2>用车场景</h2>
        <div class="options-grid">
          <div class="option-card" 
               :class="{ active: form.scenario === 0 }"
               @click="form.scenario = 0">
            <div class="option-content">
              <div class="option-title">高速为主</div>
              <div class="option-score">0 分</div>
            </div>
          </div>
          <div class="option-card" 
               :class="{ active: form.scenario === 1 }"
               @click="form.scenario = 1">
            <div class="option-content">
              <div class="option-title">高速市区各一半</div>
              <div class="option-score">1 分</div>
            </div>
          </div>
          <div class="option-card" 
               :class="{ active: form.scenario === 2 }"
               @click="form.scenario = 2">
            <div class="option-content">
              <div class="option-title">市区为主偶尔高速</div>
              <div class="option-score">2 分</div>
            </div>
          </div>
          <div class="option-card" 
               :class="{ active: form.scenario === 3 }"
               @click="form.scenario = 3">
            <div class="option-content">
              <div class="option-title">只跑市区</div>
              <div class="option-score">3 分</div>
            </div>
          </div>
        </div>
      </div>

      <!-- 4. 用车城市 -->
      <div class="form-section">
        <h2>用车城市</h2>
        <div class="options-grid">
          <div class="option-card" 
               :class="{ active: form.city === 0 }"
               @click="form.city = 0">
            <div class="option-content">
              <div class="option-title">新疆西藏不包邮地区</div>
              <div class="option-score">0 分</div>
            </div>
          </div>
          <div class="option-card" 
               :class="{ active: form.city === 1 }"
               @click="form.city = 1">
            <div class="option-content">
              <div class="option-title">东北内蒙西北地区</div>
              <div class="option-score">1 分</div>
            </div>
          </div>
          <div class="option-card" 
               :class="{ active: form.city === 2 }"
               @click="form.city = 2">
            <div class="option-content">
              <div class="option-title">其他非一线城市</div>
              <div class="option-score">2 分</div>
            </div>
          </div>
          <div class="option-card" 
               :class="{ active: form.city === 3 }"
               @click="form.city = 3">
            <div class="option-content">
              <div class="option-title">一线城市</div>
              <div class="option-score">3 分</div>
            </div>
          </div>
        </div>
      </div>

      <!-- 5. 购买方式 -->
      <div class="form-section">
        <h2>购买方式</h2>
        <div class="options-grid">
          <div class="option-card" 
               :class="{ active: form.purchaseType === 1 }"
               @click="form.purchaseType = 1">
            <div class="option-content">
              <div class="option-title">首购</div>
              <div class="option-score">1 分</div>
            </div>
          </div>
          <div class="option-card" 
               :class="{ active: form.purchaseType === 2 }"
               @click="form.purchaseType = 2">
            <div class="option-content">
              <div class="option-title">换购</div>
              <div class="option-score">2 分</div>
            </div>
          </div>
          <div class="option-card" 
               :class="{ active: form.purchaseType === 3 }"
               @click="form.purchaseType = 3">
            <div class="option-content">
              <div class="option-title">增购</div>
              <div class="option-score">3 分</div>
            </div>
          </div>
        </div>
      </div>

      <!-- 结果展示 -->
      <div class="result-section" v-if="result">
        <div class="result-card">
          <div class="result-title">推荐结果</div>
          <div class="result-content" :class="resultType">{{ result }}</div>
          <div class="total-score">总分：{{ total }} 分</div>
        </div>
      </div>
    </el-form>
  </div>
</template>

<script>
import { defineComponent, reactive, ref, computed, watch } from 'vue'

export default defineComponent({
  name: 'CarRecommendation',
  setup() {
    const form = reactive({
      mileage: 0,
      charging: 0,
      scenario: 0,
      city: 0,
      purchaseType: 1
    })

    const result = ref('')
    const resultType = ref('info')
    const total = computed(() => {
      return form.mileage + form.charging + form.scenario + form.city + form.purchaseType
    })

    watch(total, (newTotal) => {
      if (newTotal <= 6) {
        result.value = '推荐购买油车'
        resultType.value = 'success'
      } else if (newTotal >= 7 && newTotal < 11) {
        result.value = '推荐购买电车'
        resultType.value = 'warning'
      } else {
        result.value = '无脑冲电车'
        resultType.value = 'info'
      }
    }, { immediate: true })

    return {
      form,
      result,
      resultType,
      total
    }
  }
})
</script>

<style>
.car-recommendation {
  max-width: 800px;
  margin: 20px auto;
  padding: 20px;
}

h1 {
  text-align: center;
  font-size: 24px;
}

.subtitle {
  text-align: center;
  margin-bottom: 60px;
  font-size: 18px;
  color: #666;
  margin-top: 10px;
}

.subtitle p{
  margin: 0 0 5px 0;
}

.subtitle a{
  color: #666;
}

.subtitle a:hover{
  color: #409eff;
}

h2 {
  margin: 20px 0;
  font-size: 18px;
  color: #333;
}

.form-section {
  margin-bottom: 30px;
}

.options-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 15px;
}

.option-card {
  border: 2px solid #dcdfe6;
  border-radius: 8px;
  padding: 15px;
  cursor: pointer;
  transition: all 0.3s;
  background: #fff;
}

.option-card.active {
  border-color: #409eff;
  background: #ecf5ff;
}

.option-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
}

.option-title {
  font-size: 16px;
  text-align: center;
}

.option-score {
  font-size: 14px;
  color: #666;
}

.result-section {
  margin-top: 40px;
  text-align: center;
}

.result-card {
  background: #fff;
  border-radius: 12px;
  padding: 25px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.result-title {
  font-size: 20px;
  color: #333;
  margin-bottom: 15px;
}

.result-content {
  font-size: 32px;
  font-weight: bold;
  margin: 20px 0;
}

.result-content.success {
  color: #67c23a;
}

.result-content.warning {
  color: #e6a23c;
}

.result-content.info {
  color: #409eff;
}

.total-score {
  font-size: 24px;
  color: #666;
  margin-top: 15px;
}

@media (max-width: 600px) {
  .car-recommendation {
    padding: 10px;
  }
  
  .option-card {
    padding: 10px;
  }
  
  .option-title {
    font-size: 14px;
  }
  
  .option-score {
    font-size: 12px;
  }
  
  .result-content {
    font-size: 28px;
  }
  
  .total-score {
    font-size: 20px;
  }
}
</style> 