<script>
export default {
  components: {
  },
  data() {
    return {
      cnt:0,
      isChecked: false,
      isDark: false,
      textColor: '#000000',
      hip: "src/assets/hip.jpg", 
      cont: "src/assets/cont.jpg", 
      ballet: "src/assets/ballet.jpg", 
      exp: "src/assets/exp.webp", 
      vals: "src/assets/vals.jpg", 
      tango: "src/assets/tango.png", 
      nar: "src/assets/nar.jpg", 
      street: "src/assets/street.jpg",
      funk: "src/assets/funk.png",
      img: "src/assets/danc.png",
      logo: "src/assets/logo.jpg",
      inputValue: "",
      example: "",
      blocks: [true, true, true, true, true, true, true, true, true],
      reviews: [
        { id: 1, author: "Анна П.", comment: "Отличный курс по хип-хопу!", rating: 5, isRecommended: true },
        { id: 2, author: "Игорь C.", comment: "Занятия по джаз-фанку классные", rating: 4, isRecommended: true },
        { id: 3, author: "Елена Ж.", comment: "очень плохой зал", rating: 2, isRecommended: false },
        { id: 4, author: "Дмитрий В.", comment: "Экспериментал превзошел все ожидания.", rating: 5, isRecommended: true },
        { id: 5, author: "Ольга H.", comment: "Очень слабый коллектив", rating: 3, isRecommended: false }
      ],
      words: {
        "энергичный": {
          example: "Хип-хоп, джаз-фанк, стрит дэнс, джаз"
        },
        "медленный": {
          example: "вальс, контемпорари"
        },
        "плавный": {
          example: "балет, контемп"
        },
        "парный": {
          example: "вальс, танго"
        }
      }
    };
  },
  methods: {
    handleInput() {
      let word = this.words[this.inputValue];
      if (word) {
        this.example = word.example;
      } else {
        this.example = "К сожалению, не нашли ничего подходящего для вас";
      }
    },
    deleteReview(id) {
      let newArray = [];
      for (let i = 0; i < this.reviews.length; i++) {
        if (this.reviews[i].id != id) {
          newArray.push(this.reviews[i]);
        }
      }
      this.reviews = newArray;
    }
  }
};
</script>

<template>
  <header>
    <div class = "logo" :style="{ backgroundImage: `url(${logo})` }"> </div>
    <div class = "tit">
      <h2 >IDance</h2>
      <h4>  школа танцев</h4>
    </div>
    <div class = "th">
      <input type="checkbox" id="theme"  v-model="isChecked" @click="textColor = (textColor === '#000000' ? '#ff4d6d' : '#000000')">
      <label for="theme"> Тёмная тема</label>
    </div>
  </header>

  <main class="container" :style="{ backgroundColor: isChecked ? '#121214' : '#f8f9fa'  }">
    <div class = "img" :style="{ backgroundImage: `url(${img})` }"> </div>

    <div class="row" :style="{ color: textColor }">
      <h3 class = "directions" :style="[
      {borderRadius: '10px'},
      {color: isChecked ? ' #ff4d6d' : '#293133'  },
      {marginTop: '20px'}
      ]"> Направления </h3>
      <h6  :style="{color: isChecked ? ' #ff4d6d' : '#293133'  }"> вам понравилось направлений: <span>{{ cnt }}</span></h6>
      <button  @click="blocks = [true, true, true, true, true, true, true, true, true]" :style="{
        backgroundColor: 'rgba(44, 54, 56, 70)', 
        color: '#ffffff',  
        borderRadius: '4px', 
        cursor: 'pointer',
        transition: 'all 0.2s ease' 
      }"> Очистить корзину</button>

      <div class="col-1 card" v-if="blocks[0]" :style="[ {color: textColor }, {borderColor: isChecked ? ' #ff4d6d' : '#293133'}]">
        <div class = "image">
          <img class = "dir" :src="hip"/>
        </div>
        <p class = "descprition"> Хип-хоп</p>
        <div class = "btns">
          <button class = "like" @click="cnt++"></button>
          <button class = "dislike" @click="blocks[0] = false"> </button>
        </div>
      </div>

      <div class="col-2 card" v-if="blocks[1]" :style="[ {color: textColor }, {borderColor: isChecked ? ' #ff4d6d' : '#293133'}]">
        <div class = "image">
          <img class = "dir" :src="funk"/>
        </div>
        <p> Джаз-фанк</p>
        <div class = "btns">
          <button class = "like" @click="cnt++"></button>
          <button class = "dislike"  @click="blocks[1] = false"> </button>
        </div>

      </div>

      <div class="col-3 card" v-if="blocks[2]" :style="[ {color: textColor }, {borderColor: isChecked ? ' #ff4d6d' : '#293133'}]">
        <div class = "image">
          <img class = "dir" :src="cont"/>
        </div>
        <p> Джаз</p>
        <div class = "btns">
          <button class = "like" @click="cnt++"></button>
          <button class = "dislike"  @click="blocks[2] = false"> </button>
        </div>
      </div>

      <div class="col-4 card" v-if="blocks[3]" :style="[ {color: textColor }, {borderColor: isChecked ? ' #ff4d6d' : '#293133'}]">
        <div class = "image">
          <img class = "dir" :src="ballet"/>
        </div>
        <p class = "descprition">Балет</p>
        <div class = "btns">
          <button class = "like" @click="cnt++"></button>
          <button class = "dislike"  @click="blocks[3] = false"> </button>
        </div>
      </div>

      <div class="col-5 card" v-if="blocks[4]" :style="[ {color: textColor }, {borderColor: isChecked ? ' #ff4d6d' : '#293133'}]">
        <div class = "image">
          <img class = "dir" :src="exp"/>
        </div>
        <p>Экспериментал</p>
        <div class = "btns">
          <button class = "like" @click="cnt++"></button>
          <button class = "dislike"  @click="blocks[4] = false"> </button>
        </div>
      </div>

      <div class="col-6 card" v-if="blocks[5]" :style="[ {color: textColor }, {borderColor: isChecked ? ' #ff4d6d' : '#293133'}]">
        <div class = "image">
          <img class = "dir" :src="vals"/>
        </div>
        <p> Вальс</p>
        <div class = "btns">
          <button class = "like" @click="cnt++"></button>
          <button class = "dislike"  @click="blocks[5] = false"> </button>
        </div>
      </div>
      <div class="col-4 card" v-if="blocks[6]" :style="[ {color: textColor }, {borderColor: isChecked ? ' #ff4d6d' : '#293133'}]">
        <div class = "image">
          <img class = "dir" :src="tango"/>
        </div>
        <p class = "descprition">Танго</p>
        <div class = "btns">
          <button class = "like" @click="cnt++"></button>
          <button class = "dislike"  @click="blocks[6] = false"> </button>
        </div>
      </div>

      <div class="col-5 card" v-if="blocks[7]" :style="[ {color: textColor }, {borderColor: isChecked ? ' #ff4d6d' : '#293133'}]">
        <div class = "image">
          <img class = "dir" :src="nar"/>
        </div>
        <p>Народные танцы</p>
        <div class = "btns">
          <button class = "like" @click="cnt++"></button>
          <button class = "dislike"  @click="blocks[7] = false"> </button>
        </div>
      </div>

      <div class="col-6 card" v-if="blocks[8]" :style="[ {color: textColor }, {borderColor: isChecked ? ' #ff4d6d' : '#293133'}]">
        <div class = "image">
          <img class = "dir" :src="street"/>
        </div>
        <p> Street dance</p>
        <div class = "btns">
          <button class = "like" @click="cnt++"></button>
          <button class = "dislike"  @click="blocks[8] = false"> </button>
        </div>
      </div>

      <div class = "tr" :style="{ color: textColor }">
        <h3 :style="{ color: textColor }"> А какой стиль подойдёт вам?</h3>
        <p> энергичный? <br> 
          медленный? <br> 
          любите плавные движения или может быть хотите танцевать в паре?</p>
        <input class = "inp" v-model="inputValue" @input="handleInput">
        <div class ="result"></div>
        <div>
          <p>{{ example }}</p>
        </div>
      </div>
      <div>
        <h2>Отзывы клиентов</h2>
        <div v-for="item in reviews">
          <div class="review-card" :style="[{border: '1px solid #293133'}, { borderRadius: '20px' }, { borderColor: 'black' }, {marginTop: '10px'}, {height: '190px'}]">
            <p class="user-name" :style="[{marginLeft:'10px'}]">{{ item.author }}</p>
            <p class="review-text">«{{ item.comment }}»</p>
            <div class="rating">Оценка:{{ item.rating }}/ 5</div>
            <p class="recommendation">Рекомендует: <span>{{ item.isRecommended ? 'Да' : 'Нет' }}</span></p>
            <button @click="deleteReview(item.id)" :style="{ backgroundColor: '#293133', color: '#ffffff', border: '1px solid #293133',borderRadius: '4px', marginTop: '10px', marginLeft:'10px'}">
              Отзыв не интересен
            </button>
          </div>
        </div>
        </div>
    </div>
  </main>
</template>

<style>
</style>