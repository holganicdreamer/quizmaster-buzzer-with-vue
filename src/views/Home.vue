<template>
  <div>
    <div class="header">
      <a href="/">HOLGANIC DREAMER</a>&nbsp;-&nbsp;<a href="/software/quizmasterbuzzer">クイズ司会者用ブザー</a>
    </div>
    <ul>
      <li class="question" @click="clickQuestion">出題</li>
      <li class="correct" @click="clickCorrect">正解</li>
      <li class="wrong" @click="clickWrong">不正解</li>
    </ul>
    <div class="footer">
      Sound by <a href="https://otologic.jp/" target="_blank">OtoLogic</a>
    </div>
  </div>
</template>

<script>
import { Howl } from 'howler'
import BuzzerQuestion from "../assets/buzzerQuestion.mp3"
import BuzzerCorrect from "../assets/buzzerCorrect.mp3"
import BuzzerWrong from "../assets/buzzerWrong.mp3"

export default {
  name: 'home',
  data: function() {
    return {
      buzzerQuestion: null,
      buzzerCorrect: null,
      buzzerWrong: null,
      date: null,
    }
  },
  methods: {
    clickQuestion() {
      this.buzzerQuestion.play()
    },
    clickCorrect() {
      this.buzzerCorrect.play()
    },
    clickWrong() {
      this.buzzerWrong.play()
    },
  },
  mounted () {
    this.buzzerQuestion = new Howl({ src: [BuzzerQuestion] })
    this.buzzerCorrect = new Howl({ src: [BuzzerCorrect] })
    this.buzzerWrong = new Howl({ src: [BuzzerWrong] })
  },
}
</script>

<style>
.header {
  font-family: 'Lato', 'Noto Sans JP', '游ゴシック Medium', '游ゴシック体', 'Yu Gothic Medium', YuGothic, 'ヒラギノ角ゴ ProN', 'Hiragino Kaku Gothic ProN', 'メイリオ', Meiryo, 'ＭＳ Ｐゴシック', 'MS PGothic', sans-serif;
  font-weight: 900;
  text-align:left;
  font-size: 12px;
}
.header a {
  text-decoration: none;
  color: #777777;
  font-weight: 600;
}
.footer {
  font-size: 12px;
}
.footer a {
  text-decoration: none;
  color: #777777;
  font-weight: 600;
}
ul {
  margin: 0;
  padding-left: 0;
  display: flex;
  width: 100%;
  margin: 10px auto;
}
li {
  list-style: none;
  font-family: 'Lato', 'Noto Sans JP', '游ゴシック Medium', '游ゴシック体', 'Yu Gothic Medium', YuGothic, 'ヒラギノ角ゴ ProN', 'Hiragino Kaku Gothic ProN', 'メイリオ', Meiryo, 'ＭＳ Ｐゴシック', 'MS PGothic', sans-serif;
  width: 100%;
  margin: 0 5px;
  color: white;
  line-height: 75vh;
  font-size: 2rem;
}
.question {
  background: blue;
}
.correct {
  background: green;
}
.wrong {
  background: red;
}
</style>

