<template>
  <div id="playlist">
    <div id="secborder" ref="playlist" @click="changeSource">
        <div 
            class="song" 
            url-value="src/assets/music/HanhLangCuHaNho.mp3" 
            picture-value="src/assets/imgs/hanhlangcu.jpg">Hành Lang Cũ - Long Nón Lá
        </div> 
        <div 
            class="song" 
            url-value="src/assets/music/CoThamKhongVe.mp3" 
            picture-value="src/assets/imgs/cothamkhongve.jpg">Cô Thắm Không Về - Phát Hồ
        </div>
        <div 
            class="song" 
            url-value="src/assets/music/Didaudethayhoabay.mp3" 
            picture-value="src/assets/imgs/didaudethayhoabay.jpg">Đi đâu để thấy hoa bay - Nguyễn Hoàng Dũng
        </div>   
    </div>
  </div>
</template>
<script>
    import { bus } from '../main';
    export default {
        name: 'playlist',
        props : {
            currentSong: {
                type : String
            },
            currentImage: {
                type : String
            }
        },
        data () {
            return {
            }
        },

        methods: {
            changeSource : function(e) {
            const self = this;
            let songValue = e.target.attributes[1].value;
            let songImage = e.target.attributes[2].value;
            self.$emit('updateData', [songValue, songImage]);
            self.$emit('reload');
            }
        }
    }
</script>
<style scoped>
#secborder {
    border: 10px solid white;
    border-radius: 15px;
    margin: 2rem 0.5rem;
    background: black;
    height: 35rem;
    width: 40%;
    float: right;
}
.song {
    width: 100%;
    height: 10%;
    padding: 0.5em;
    border-bottom: 0.5px solid #172951;
    font-size: 1.5rem;
    font-weight: bold;
    text-align: center;
    color: white;
    cursor: pointer;
}
</style>