<template>
  <div class="wrapper-form">
    <div class="container-form">
      <div class="head">
        <div class="title">联系我们</div>
        <div class="desc">请真实填写如下内容，我们会在一个工作日内与您联系。</div>
      </div>
      <div class="main">
        <div class="form">
          <div class="row">
            <div class="col">
              <div class="input input-text" :class="info.name.isError ? 'is-error' : ''">
                <label>称呼</label>
                <input name="name" placeholder="请输入您的名字" type="text" v-model.trim="info.name.con">
                <div class="input-info">必填</div>
              </div>
            </div>
            <div class="col">
              <div class="input input-text" :class="info.company.isError ? 'is-error' : ''">
                <label>公司</label>
                <input
                  name="company"
                  placeholder="请输入公司或品牌名"
                  type="text"
                  v-model.trim="info.company.con"
                >
                <div class="input-info"></div>
              </div>
            </div>
          </div>
          <div class="row">
            <div class="col">
              <div class="input input-text" :class="info.tel.isError ? 'is-error' : ''">
                <label>电话</label>
                <input name="tel" placeholder="请输入手机号或座机号" type="text" v-model.trim="info.tel.con">
                <div class="input-info">必填</div>
              </div>
            </div>
            <div class="col">
              <div class="input input-text" :class="info.email.isError ? 'is-error' : ''">
                <label>邮箱</label>
                <input name="mail" placeholder="请输入您的邮箱" type="text" v-model.trim="info.email.con">
                <div class="input-info"></div>
              </div>
            </div>
          </div>
          <div class="row">
            <div class="col">
              <div class="input input-text" :class="info.desc.isError ? 'is-error' : ''">
                <label>项目描述</label>
                <textarea class="textarea" placeholder="简单地描述一下您的项目" v-model="info.desc.con"></textarea>
                <div class="input-info">必填</div>
              </div>
            </div>
          </div>
          <div class="row">
            <div class="col btn-wrap">
              <button @click="submitInfo" class="btn">{{btnText}}</button>
            </div>
          </div>
        </div>
        <div class="info">
          <div class="item">
            <svg
              version="1.1"
              viewBox="0 0 1026 1024"
              xmlns="http://www.w3.org/2000/svg"
              xmlns:xlink="http://www.w3.org/1999/xlink"
            >
              <path
                d="M981.035477 758.537463c-26.597403-26.085914-60.355644-50.637363-83.372628-67.004995-31.200799-21.994006-63.936064-42.453546-92.57942-57.286714-45.010989-23.528472-63.936064-26.597403-74.165835-26.597402-19.948052 0-37.338661 10.741259-52.171828 31.712287-9.718282 14.321678-17.390609 31.712288-25.062937 49.102897-5.114885 12.275724-13.298701 30.689311-19.436563 38.361639l-2.045954 2.557442-3.068931-0.511488c-6.137862-1.534466-29.666334-8.695305-80.303697-42.965035-39.896104-27.108891-83.372627-62.401598-116.61938-94.625375-31.712288-32.735265-67.004995-76.211788-94.625375-116.107892-34.26973-50.637363-41.942058-74.165834-42.965035-80.303696l-0.511488-3.068931 2.557442-2.045954c7.672328-6.137862 26.085914-13.81019 38.361639-19.436564 16.879121-7.160839 34.26973-14.833167 49.102897-25.062937 20.971029-14.321678 31.712288-32.223776 31.712287-52.171828 0-10.22977-2.557443-29.154845-26.597402-74.165834-14.833167-28.131868-35.292707-60.867133-57.286714-92.579421-16.367632-23.528472-41.430569-56.775225-67.004995-83.372627-28.643357-29.666334-49.614386-42.453546-69.050949-42.453546-48.591409 0-106.901099 72.631369-123.780219 95.136863-21.482517 28.643357-72.11988 103.320679-72.119881 173.394605 0 65.470529 43.988012 150.377622 80.815185 210.733267 49.614386 80.815185 118.665335 167.768232 193.854146 244.491508l25.062937 25.062937c77.234765 75.188811 164.187812 143.728272 244.491509 193.854146 59.844156 36.827173 145.262737 80.815185 210.733266 80.815185 29.154845 0 59.332667-8.695305 86.953047-20.971029v-0.511488c8.183816-4.091908 14.321678-12.787213 14.321679-22.505495 0-13.81019-11.252747-25.574426-25.574426-25.574426-4.091908 0-7.672328 1.022977-11.252747 2.557443-23.528472 10.22977-46.033966 15.344655-63.936064 15.344655-41.430569 0-108.435564-26.597403-184.135864-73.142857-77.746254-47.568432-161.118881-114.061938-235.796204-186.693306l-24.03996-24.039961c-72.631369-74.677323-139.124875-158.04995-186.693307-235.796203-46.545455-75.7003-73.142857-142.705295-73.142857-184.135864 0-36.827173 22.505495-88.999001 59.844156-139.636364 16.367632-21.994006 34.26973-42.453546 51.148851-56.775225 17.902098-15.856144 28.643357-19.436563 31.200799-20.45954l2.045954-0.511489 2.045954 1.022977c11.252747 5.114885 46.033966 34.781219 97.182818 109.458542 19.436563 28.131868 37.338661 57.286713 50.637362 82.34965 16.367632 31.200799 19.436563 45.010989 19.948052 48.591409l0.511489 2.045954-1.022977 1.534465c-1.022977 2.045954-4.603397 5.626374-13.81019 11.252747-9.718282 6.137862-23.016983 11.252747-35.292707 16.879121-14.833167 6.649351-30.689311 13.298701-42.965035 21.482518-19.436563 12.787213-28.643357 28.131868-28.643357 46.033966 0 9.206793 0.511489 36.315684 52.683317 112.527472 29.154845 42.453546 66.493506 88.487512 100.251748 123.268732l0.511488 0.511488c34.781219 33.758242 80.815185 71.608392 123.268732 100.251748 76.211788 51.66034 103.320679 52.683317 112.527472 52.683317h1.022977c17.390609 0 32.735265-9.718282 45.010989-28.643357 8.183816-12.275724 14.833167-27.62038 21.482518-42.965035 5.626374-12.275724 10.741259-25.574426 16.879121-35.292707 5.114885-8.695305 8.695305-12.275724 11.252747-13.81019l1.534465-1.022977 2.045954 0.511489c3.58042 0.511489 16.879121 3.58042 48.591409 19.948052 24.551449 12.787213 54.217782 31.200799 82.34965 50.637362 74.677323 51.148851 103.832168 85.93007 109.458542 97.182818l1.022977 2.045954-0.511489 2.045954c-1.022977 2.557443-5.114885 13.298701-20.45954 31.200799-5.626374 6.649351-11.764236 13.298701-18.925075 19.948052l-0.511489 0.511488c-4.603397 4.603397-7.160839 10.741259-7.160839 17.39061 0 13.81019 11.252747 25.574426 25.574426 25.574425 7.160839 0 13.298701-2.557443 17.902098-7.160839 26.597403-25.574426 55.240759-59.844156 55.240759-90.021978-2.045954-20.971029-15.344655-42.453546-44.4995-70.585414z"
                p-id="8244"
              ></path>
            </svg>
            <span>+86 17187488188</span>
          </div>
          <div class="item">
            <svg
              version="1.1"
              viewBox="0 0 1025 1024"
              xmlns="http://www.w3.org/2000/svg"
              xmlns:xlink="http://www.w3.org/1999/xlink"
            >
              <path
                d="M872.557745 160.060954l-720.137162 0c-66.384034 0-120.021155 53.626887-120.021155 119.878908l0 464.274803c0 66.249975 53.637121 119.881978 120.021155 119.881978l720.137162 0c66.136382 0 120.022178-53.632004 120.022178-119.881978L992.579923 279.939862C992.580946 213.687841 938.694127 160.060954 872.557745 160.060954zM928.565979 744.214665c0 30.808111-25.129512 55.875199-56.007211 55.875199l-720.137162 0c-30.881792 0-56.007211-25.066064-56.007211-55.875199L96.414395 279.939862c0-30.750803 25.126442-55.878269 56.007211-55.878269l720.137162 0c30.878722 0 56.007211 25.127466 56.007211 55.878269L928.565979 744.214665z"
                p-id="9700"
              ></path>
              <path
                d="M833.235318 376.197683l-320.745131 206.758702-320.872027-206.758702c-14.881633-9.50083-34.633413-5.255953-44.258069 9.562232-9.504924 14.874469-5.256976 34.685604 9.624656 44.249883l338.190268 217.887691c5.248789 3.433357 11.315239 5.061515 17.315171 5.061515 6.003002 0 12.063312-1.628158 17.316195-5.061515l338.058255-217.887691c14.881633-9.564279 19.196098-29.375413 9.571442-44.249883C867.863614 370.883399 847.926606 366.696853 833.235318 376.197683z"
                p-id="9701"
              ></path>
            </svg>
            <span>fon@jue.sh</span>
          </div>
          <div class="item">
            <svg
              version="1.1"
              viewBox="0 0 1024 1024"
              xmlns="http://www.w3.org/2000/svg"
              xmlns:xlink="http://www.w3.org/1999/xlink"
            >
              <path
                d="M226.048 125.286c164.297-164.7 430.674-164.7 594.954 0 164.308 164.704 126.054 431.749-38.25 596.449l-259.219 298.213-259.229-298.213c-164.311-164.7-202.551-431.746-38.257-596.449zM523.53 911.507l205.155-243.985c134.414-134.755 172.663-353.26 38.25-488.011-134.438-134.755-352.375-134.755-486.799 0-134.42 134.752-96.171 353.253 38.253 488.011l205.141 243.985zM523.53 193.461c-105.615 0-191.232 85.839-191.232 191.71 0 105.868 85.617 191.706 191.232 191.706 105.632 0 191.229-85.839 191.229-191.706 0-105.868-85.596-191.71-191.229-191.71zM523.53 500.186c-63.369 0-114.739-51.483-114.739-115.016s51.367-115.019 114.739-115.019c63.372 0 114.749 51.487 114.749 115.019s-51.377 115.016-114.749 115.016z"
                p-id="7514"
              ></path>
            </svg>
            <span>上海市徐汇区田林东路75号（汇阳广场）75号20楼</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      btnText: '发 送',
      info: {
        name: {
          con: '',
          isError: false
        },
        company: {
          con: '',
          isError: false
        },
        tel: {
          con: '',
          isError: false
        },
        email: {
          con: '',
          isError: false
        },
        desc: {
          con: '',
          isError: false
        }
      }
    }
  },
  methods: {
    submitInfo() {
      if(this.info.name.con == ''){
        this.info.name.isError = true
        return false
      }
      if(this.info.tel.con == ''){
        this.info.tel.isError = true
        return false
      }

      this.btnText = '发送中'

      this.$axios.setHeader('Accept', 'application/json')
      this.$axios.setHeader('Content-Type', 'application/json')
      this.$axios
        .post('https://api.jue.sh/mail/sent/fromjue', {
          name: this.info.name.con,
          company: this.info.company.con,
          tel: this.info.tel.con,
          email: this.info.email.con,
          desc: this.info.desc.con
        })
        .then(res => {
          if (res.status == 201) {
            this.btnText = '发送成功'
            setTimeout(() => {
              this.$emit('changeMenu')
              this.info.name.con = ''
              this.info.company.con = ''
              this.info.tel.con = ''
              this.info.email.con = ''
              this.info.desc.con = ''
              this.btnText = '发 送'
            }, 1500)
          }
        })
    }
  },
  watch:{
    'info.name.con': {
      handler(){
        let _this = this
        if(this.info.name.con != ''){
          _this.info.name.isError = false
        }
      },
      immediate: true
    },
    'info.tel.con': {
      handler(){
        let _this = this
        if(this.info.tel.con != ''){
          _this.info.tel.isError = false
        }
      },
      immediate: true
    }
  }
}
</script>

<style lang="less" scoped>
.wrapper-form {
  position: fixed;
  display: flex;
  width: 100%;
  height: 100%;
  background: #1a1a1a;
  z-index: 10;
  top: 0;
  left: 0;
  overflow-y: auto;
}
.head {
  color: #808080;
  padding: 40px 40px 100px 100px;
  .title {
    font-size: 30px;
    font-weight: bold;
  }
  .desc {
    padding: 10px 0;
    line-height: 1.5;
  }
}

.main {
  display: flex;
  .form {
    flex: 1;
    padding: 0 80px;
  }
  .info {
    width: 300px;
    .item {
      padding: 10px 0;
      display: flex;
      align-items: center;
      svg {
        fill: #fff;
        width: 20px;
        display: inline-block;
      }
      span {
        color: #fff;
        flex: 1;
        padding-left: 20px;
        font-size: 13px;
        line-height: 1.5;
      }
    }
  }
}

.row {
  display: flex;
  justify-content: space-between;
  .col {
    flex: 1;
    padding: 20px 20px;
  }
}

.input {
  color: #808080;
  label {
    font-size: 12px;
    font-weight: bolder;
    display: block;
    margin-bottom: 5px;
  }
  input,
  .textarea {
    display: block;
    width: 100%;
    color: #fff;
    border: 0;
    border-bottom: 2px solid #fff;
    outline: 0;
    font-size: 14px;
    padding: 10px 0;
    background: none;
  }
  .textarea {
    min-height: 80px;
  }
  .input-info {
    font-size: 12px;
    text-align: right;
    padding: 5px 0 0 0;
  }
  &.is-error {
    color: #eb4c49;
    input,
    .textarea {
      border-bottom-color: #eb4c49;
    }
    ::-webkit-input-placeholder {
      color: #eb4c49;
    }
  }
}
.btn-wrap {
  text-align: right;
}
.btn {
  white-space: nowrap;
  display: inline-block;
  vertical-align: middle;
  outline: 0;
  padding: 15px 25px;
  background-color: #fff;
  font-size: 15px;
  font-weight: bolder;
  border: none;
  cursor: pointer;
  &:hover {
    background-color: #eeeada;
  }
  &:after {
    content: '';
    display: inline-block;
    margin-left: 2em;
    width: 3.33333333em;
    height: 2px;
    margin-top: -2px;
    vertical-align: middle;
    background: #1a1a1a;
  }
}

@media only screen and (max-width: 768px) {
  .main {
    flex-direction: column;
    .info {
      width: 100%;
      padding: 80px;
    }
  }
}

@media only screen and (max-width: 414px) {
  .head {
    padding: 120px 0 50px;
    .title {
      font-size: 20px;
    }
    .desc {
      font-size: 13px;
    }
  }
  .main {
    .form {
      padding: 0;
    }
    .info {
      padding: 50px 0;
    }
  }
  .row {
    flex-direction: column;
    .col {
      width: 100%;
      padding: 10px 0;
    }
  }
}
</style>

