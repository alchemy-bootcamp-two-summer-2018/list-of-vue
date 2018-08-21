<template>
  <div class="formcontent">
    <div class="welcome-text">Create your celebrity profile</div>   
    <form v-on:submit.prevent="handleSubmit">
      <div class="form-contents">
        <div class="form-questions">

          <section class="input-container">
              <label> <h3>1. Name </h3> 
              <input type="text" placeholder="What is your name?" v-model="name" >
              </label>
              <br>
          </section>

          <label> <h3 class="h3margin">2. What is your celebrity status? </h3> </label>
              <div class="radio-flex-income">

                  <input type="radio" v-model="celebStatus" id="statusradio-1" value="Retired child star" checked/>
                  <label class="radiolabel" for="statusradio-1">Retired child star</label>

                  <input type="radio" v-model="celebStatus" id="statusradio-2" value="Infamous but really just misunderstood" />
                  <label class="radiolabel" for="statusradio-2">Infamous but really just misunderstood</label>

                  <input type="radio" v-model="celebStatus" id="statusradio-3" value="Famous for being racist" />
                  <label class="radiolabel" for="statusradio-3">Famous for being racist</label>

                  <input type="radio" v-model="celebStatus" id="statusradio-4" value="All press is good press"/>
                  <label class="radiolabel" for="statusradio-4">All press is good press</label>

                  <input type="radio" v-model="celebStatus" id="statusradio-5" value="Multihyphenate Actor/Director/Producer/Musician"/>
                  <label class="radiolabel" for="statusradio-5">Multihyphenate Actor/Director/Producer/Musician</label>

                  <input type="radio" v-model="celebStatus" id="statusradio-6" value="Friends with Bono"/>
                  <label class="radiolabel" for="statusradio-6">Friends with Bono</label>
              </div>

              <section class="input-container">
                      <label> <h3>3. How fertile are you? </h3></label>
                      <!-- <input type ="range" max="5" min="1"
                      oninput="document.getElementById('fertilityRangeLabel').innerHTML = this.value;"
                      step="1" name="rangeVal" id="fertility" value="3">
                      <br> -->
                      <TouchRange
                          :min="1"
                          :max="5"
                          :step="1"
                          v-model="fertility"
                          oninput="document.getElementById('fertilityRangeLabel').innerHTML = this.value;"
                          />
                      <em id="fertilityRangeLabel" style="font-style: normal;"></em>
              </section>

              <label> <h3 class="h3margin"> 4. What is your favorite book? </h3> </label>
              <div class="radio-flex-book">

                  <input type="radio" v-model="book" id="bookradio-1" value="Atlas Shrugged by Ayn Rand" checked/>
                  <label class="radiolabel" for="bookradio-1">Atlas Shrugged by Ayn Rand</label>

                  <input type="radio" v-model="book" id="bookradio-2" value="An Inconvenient Truth by Al Gore"/>
                  <label class="radiolabel" for="bookradio-2">An Inconvenient Truth by Al Gore</label>

                  <input type="radio" v-model="book" id="bookradio-3" value="Awaken the Giant Within by Tony Robbins" >
                  <label class="radiolabel" for="bookradio-3">Awaken the Giant Within by Tony Robbins</label>

                  <input type="radio" v-model="book" id="bookradio-4" value="The Bible by God"/>
                  <label class="radiolabel" for="bookradio-4">The Bible by God</label>

                  <input type="radio" v-model="book" id="bookradio-5" value="If I Did It by OJ Simpson" />
                  <label class="radiolabel" for="bookradio-5">If I Did It by OJ Simpson</label>

                  <input type="radio" v-model="book" id="bookradio-6" value="The Boxcar Children by Gertrude Chandler Warner"/>
                  <label class="radiolabel" for="bookradio-6">The Boxcar Children by Gertrude Chandler Warner</label>

                  <input type="radio" v-model="book" id="bookradio-7" value="Leaves of Grass by Walt Whitman"/>
                  <label class="radiolabel" for="bookradio-7">Leaves of Grass by Walt Whitman</label>
              </div>

              <section class="input-container">
                  <label> <h3> 5. How would you describe yourself to a potential suitor? </h3>
                  <textarea id="textarea" placeholder="Insert bio." v-model="bio" rows="3" cols="30"></textarea><br>
                  </label>
              </section>

              <section class="input-container">
                  <label> <h3> 6. Picture </h3>
                  <input type="text" placeholder="Insert a URL of a recent picture of yourself." v-model="pic">
                  </label>
              </section>

              <section class="input-container">
                  <label><h3> 7. What ladder number do you <em> think </em> you are?</h3></label> <br>
                      <TouchRange
                          :min="0"
                          :max="10"
                          :step="1"
                          v-model="ladder_guess"
                          oninput="document.getElementById('ladderRangeLabel').innerHTML = this.value;"
                          />
                      <em id="ladderRangeLabel" style="font-style: normal;"></em>
              </section>
            </div>
        </div>

        <div class="input-button-container">
              <button>Add Celeb</button>
        </div>
    </form>
  </div>
</template>

<script>
import TouchRange from '@miyaoka/vue-touch-range';
 
export default {
  props: {
    onAdd: Function
  },
  data() {
    return {
      name: '',
      celebStatus: '',
      fertility: 0,
      book: '',
      bio: '',
      pic: '',
      ladder_guess: 0
    };
  },
  components: {
    TouchRange
  },

  methods: {
    handleSubmit() {
      const newCeleb = {
        name: this.name,
        celebStatus: this.celebStatus,
        fertility: this.fertility,
        book: this.book,
        bio: this.bio,
        pic: this.pic,
        ladder_guess: this.ladder_guess
      };
      this.onAdd(newCeleb);
      
      this.name = '';
      this.celebStatus = '';
      this.fertility = 0;
      this.book = '';
      this.bio = '';
      this.pic = '';
      this.ladder = 0;
    }
  }
};
</script>

<style>
body {
    font-weight: bold;
    text-rendering: auto;
    color: initial;
    letter-spacing: normal;
    word-spacing: normal;
    text-transform: none;
    text-indent: 0px;
    text-shadow: none;
    display: inline-block;
    text-align: start;
    margin-left: 10%;
    margin-right: 10% !important;
    font: 400 .9rem system-ui;
}

h3 {
    font-size: 1.1rem;
}


.menu-content {
    width: 100%;
    font-family: 'Yanone Kaffeesatz', sans-serif;
}

.grid2 {
    display: grid;
    grid-template-columns: 80vw;
    grid-template-rows: 14vh auto 7vh;
    grid-template-areas: 
                        'nav'
                        'formcontent'
                        'footer';
    grid-row-gap: 2vh;
}

.grid2 .nav {
    grid-area: nav;
}

.grid2 .formcontent {
    grid-area: formcontent;
    align-self: flex-end;
}

.grid2 .footer {
    grid-area: footer;
}

.form-contents {
    display: grid;
    grid-template-columns: 100%;
    grid-template-rows: 95% 5%;
    grid-template-areas: 'form-questions'
                         'input-button-container';
    /* margin-top: 10px; */
    grid-row-gap: 5vh;
    justify-content: center;
}

.form-questions {
    grid-area: form-questions;
}  

.input-button-container {
    align-self: flex-end;
    grid-area: input-button-container;
    justify-self: center;
    width: 100%;
    display: flex;
    justify-content: center;

}  
.radio-flex-income {
    display: flex;
    justify-content: space-evenly;
    margin-left: 2%;
}

.radio-flex-book {
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    margin-left: 2%;
}

#input-form-button {
    border: 3px solid #96d1f8;
    background: #e80c7a;
    padding: 14.5px 29px;
    -webkit-border-radius: 8px;
    -moz-border-radius: 8px;
    border-radius: 8px;
    color: white;
    font-size: 16px;
    text-decoration: none;
    vertical-align: middle;
}


#input-form-button:hover {
    background: #ce0b6d;
}

form {
	/* position: absolute; */
	top: 0%;
	display: flex;
	justify-content: center;
	align-items: center;
    flex-wrap: wrap;
    margin-top: 2%;
}

section.input-container-first {
    padding: 0%;
    padding-top: 0%;
}

section.input-container {
    padding: 0%;
}

section.input-container label{
    position: relative;
    display: block;
    align-items: left;
}

section.input-container label input {
    display: block;
    padding: 10px; 
    width: 100%; 
    background-color: white;
    font-weight: bold;
    color:#e80c7a;
    font: 400 .9em system-ui;
}

section.input-container label span {
    font-size: .8rem;
    color: black;
    position: absolute;
    top: 0px;
    left: 20px;
}

section.input-container label textarea {
display: block;
padding: 2%;
padding-right: 500px;
width: 100%;
background-color: white;
font-weight: bold;
color:#e80c7a;
font: 400 .9em system-ui;
}


input[type="radio"]{
    visibility: hidden;
    height: 0;
    width: 0;
  }

.radiolabel {
    display: table-cell;
    vertical-align: middle;
    text-align: center;
    cursor: pointer;
    background-color: grey;
    color: white;
    padding: 5px 10px;
    border-radius: 3px;
}

input[type="radio"]:checked + .radiolabel{
    background-color: #e80c7a;
}
  

input[type="radio"]:hover + .radiolabel{
    background-color: #e80c7a;
}
  
footer {
    width: 100%;
}

.formcontent {
  padding-bottom: 10%;
}
</style>
