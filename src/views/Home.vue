<template>
  <ul>
    <li class="question" @click="clickQuestion">出題</li>
    <li class="correct" @click="clickCorrect">正解</li>
    <li class="wrong" @click="clickWrong">不正解</li>
  </ul>
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
  line-height: 90vh;
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

