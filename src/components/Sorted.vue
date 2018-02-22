<template>
  <div class="sorted">
    <h1>Hebrew Alphabetic Sort</h1>
    <p>{{keys}}</p>
    <div class="col-md-12"> 
       <textarea class="form-control" id="exampleFormControlTextarea1" placeholder="Enter your story habibi... " rows="8" cols="50" v-model="story"></textarea>
    </div>
    <div class="col-md-12">
       <textarea class="form-control" disabled id="exampleFormControlTextarea1" rows="8" cols="50">{{sortedParagraph}}</textarea>
    </div>
  </div>
</template>

<<script>
export default {
  data(){
      return{
          story:"",
          dict : {"A" : "a", "B" : "b", "G" : "c", "D" : "d", "H" : "e", "V" : "f", "Z" : "g", "J" : "h", "T" : "i", "Y" : "j",
				"K" : "k", "L" : "l", "M" : "m", "N" : "n", "S" : "o", "I" : "p", "P" : "q", "X" : "r", "Q" : "s", "R" : "t",
        "W" : "u", "U" : "v" , "C" : "w", "E" : "x", "F" : "y", "O" : "z"}
      }
  },
  computed:{
    sortedParagraph(){
      return this.sort(this.story)
    },
    keys() {
      return Object.keys(this.dict).join(",")
    }
  },
  methods:{
    sort(paragraph){
        let mapped_paragraph = []
        paragraph = paragraph.replace(/[^\w\s]|_|\n/g, "");
        var converted_paragraph = paragraph.toUpperCase().replace(/[A-Z]/gi, m => this.dict[m]).split(" ")
        var original_paragraph = paragraph.split(" ")
        for (let i=0; i<original_paragraph.length; i+=1){
          mapped_paragraph.push([converted_paragraph[i], original_paragraph[i]])
        }

        mapped_paragraph.sort()

        var values = mapped_paragraph.map(function(item){
          return item[1];
        });
	
      	return values.join(" ")
    }
  }
}
</script>

<style>
  .sorted{
    margin-top: 60px;
  }
  .form-control{
    margin: 20px;
    padding: 10px;
  }
</style>

