<template lang="html">
  <div class="poker-tables">
    <div class="container">
      <div class="tables" style="margin-top:20px; color: rgba(0,0,0,3)" >
        <h1>Tablas Poker</h1>
        <div class="button-tables" style="margin-bottom:20px">
          <button type="button" class="btn btn-primary" @click="tableView('utg')">UTG</button>
          <button type="button" class="btn btn-secondary" @click="tableView('mp')">MP</button>
          <button type="button" class="btn btn-success" @click="tableView('co')">CO</button>
          <button type="button" class="btn btn-danger" @click="tableView('btn')">BTN</button>
          <button type="button" class="btn btn-warning" @click="tableView('sb')">SB</button>
          <button type="button" class="btn btn-info" @click="tableView('bb')">BB</button>
          <button type="button" class="btn btn-light" style="border: 1px solid silver"  @click="tableView('sqz')">SQZ</button>
          <button type="button" class="btn btn-dark"  @click="tableView('rol')">ROL</button>
        </div>
        <div class="bb-table"  v-if="bbValue">
          <h5>BB</h5>
          <div style="margin-bottom:20px">
            <button type="button" class="btn btn-primary" @click="tableViewMore('bbvsutg')">BB VS UTG </button>
            <button type="button" class="btn btn-secondary" @click="tableViewMore('bbvsmp')">BB VS MP</button>
            <button type="button" class="btn btn-success" @click="tableViewMore('bbvsco')">BB VS CO</button>
            <button type="button" class="btn btn-danger" @click="tableViewMore('bbvsbtn')">BB VS BTN</button>
            <button type="button" class="btn btn-warning" @click="tableViewMore('bbvssb')">BB VS SB</button>
          </div>
          <div class="bbvsutg-table" v-if="bbvsutgValue">
            <h5>BB VS UTG</h5>
            <img src="../assets/images/bb vs utg.jpg" height="330px">
          </div>
          <div class="bbvsmp-table" v-if="bbvsmpValue">
            <h5>BB VS MP</h5>
            <img src="../assets/images/bb vs mp.jpg" height="330px">
          </div>
          <div class="bbvsco-table" v-if="bbvscoValue">
            <h5>BB VS CO</h5>
            <img src="../assets/images/bb vs co.jpg" height="330px">
          </div>
          <div class="bbvsbtn-table" v-if="bbvsbtnValue">
            <h5>BB VS BTN</h5>
            <img src="../assets/images/bb vs btn.jpg" height="330px">
          </div>
          <div class="bbvssb-table" v-if="bbvssbValue">
            <h5>BB VS SB</h5>
            <img src="../assets/images/bb vs sb.jpg" height="330px">
          </div>
        </div>
        <div class="sb-table"  v-if="sbValue">
          <h5>SB</h5>
          <div style="margin-bottom:20px">
            <button type="button" class="btn btn-primary" @click="tableViewMore('sbor')">SB OR </button>
            <button type="button" class="btn btn-warning" @click="tableViewMore('sbvsutg')">SB VS UTG</button>
            <button type="button" class="btn btn-secondary" @click="tableViewMore('sbvsmp')">SB VS MP</button>
            <button type="button" class="btn btn-success" @click="tableViewMore('sbvsco')">SB VS CO</button>
            <button type="button" class="btn btn-danger" @click="tableViewMore('sbvsbtn')">SB VS BTN</button>
          </div>
          
          <div class="sbor-table" v-if="sborValue">
            <h5>SB OR</h5>
            <img src="../assets/images/sb or.jpg" height="330px">
          </div>
          <div class="sbvsutg-table" v-if="sbvsutgValue">
            <h5>SB VS UTG</h5>
            <img src="../assets/images/sb vs utg.jpg" height="330px">
          </div>
          <div class="sbvsmp-table" v-if="sbvsmpValue">
            <h5>SB VS MP</h5>
            <img src="../assets/images/sb vs mp.jpg" height="330px">
          </div>
          <div class="sbvsco-table" v-if="sbvscoValue">
            <h5>SB VS CO</h5>
            <img src="../assets/images/sb vs co.jpg" height="330px">
          </div>
          <div class="sbvsbtn-table" v-if="sbvsbtnValue">
            <h5>SB VS BTN</h5>
            <img src="../assets/images/sb vs btn.jpg" height="330px">
          </div>
          
        </div>

        <div class="btn-table"  v-if="btnValue">
          <h5>BTN</h5>
          <div style="margin-bottom:20px">
            <button type="button" class="btn btn-primary" @click="tableViewMore('btnor')">BTN OR </button>
            <button type="button" class="btn btn-warning" @click="tableViewMore('btnvsutg')">BTN VS UTG</button>
            <button type="button" class="btn btn-secondary" @click="tableViewMore('btnvsmp')">BTN VS MP</button>
            <button type="button" class="btn btn-success" @click="tableViewMore('btnvsco')">BTN VS CO</button>
          </div>
          
          <div class="btnor-table" v-if="btnorValue">
            <h5>BTN OR</h5>
            <img src="../assets/images/btn or.jpg" height="330px">
          </div>
          <div class="btnvsutg-table" v-if="btnvsutgValue">
            <h5>BTN VS UTG</h5>
            <img src="../assets/images/btn vs utg.jpg" height="330px">
          </div>
          <div class="btnvsmp-table" v-if="btnvsmpValue">
            <h5>BTN VS MP</h5>
            <img src="../assets/images/btn vs mp.jpg" height="330px">
          </div>
          <div class="btnvsco-table" v-if="btnvscoValue">
            <h5>BTN VS CO</h5>
            <img src="../assets/images/btn vs co.jpg" height="330px">
          </div>
        </div>

        <div class="co-table"  v-if="coValue">
          <h5>CO</h5>
          <div style="margin-bottom:20px">
            <button type="button" class="btn btn-primary" @click="tableViewMore('coor')">CO OR </button>
            <button type="button" class="btn btn-warning" @click="tableViewMore('covsutg')">CO VS UTG</button>
            <button type="button" class="btn btn-secondary" @click="tableViewMore('covsmp')">CO VS MP</button>
          </div>
          
          <div class="coor-table" v-if="coorValue">
            <h5>CO OR</h5>
            <img src="../assets/images/co or.jpg" height="330px">
          </div>
          <div class="covsutg-table" v-if="covsutgValue">
            <h5>CO VS UTG</h5>
            <img src="../assets/images/co vs utg.jpg" height="330px">
          </div>
          <div class="covsmp-table" v-if="covsmpValue">
            <h5>CO VS MP</h5>
            <img src="../assets/images/co vs mp.jpg" height="330px">
          </div>
        </div>

        <div class="mp-table"  v-if="mpValue">
          <h5>MP</h5>
          <div style="margin-bottom:20px">
            <button type="button" class="btn btn-primary" @click="tableViewMore('mpor')">MP OR </button>
            <button type="button" class="btn btn-warning" @click="tableViewMore('mpvsutg')">MP VS UTG</button>
          </div>
          
          <div class="mpor-table" v-if="mporValue">
            <h5>MP OR</h5>
            <img src="../assets/images/mp or.jpg" height="330px">
          </div>
          <div class="mpvsutg-table" v-if="mpvsutgValue">
            <h5>MP VS UTG</h5>
            <img src="../assets/images/mp vs utg.jpg" height="330px">
          </div>
        </div>

        <div class="utg-table" v-if="utgValue">
          <h5>UTG</h5>
          <img src="../assets/images/utg.jpg" height="330px">
        </div>
        <div class="sqz-table"  v-if="sqzValue">
          <h5>SQZ</h5>
          <img src="../assets/images/sqz.jpg" height="360px">
        </div>
        <div class="rol-table"  v-if="rolValue">
          <h5>ROL</h5>
          <img src="../assets/images/rol.jpg" height="380px">
        </div>
        <div class="title-tables" style="margin-top:20px; color: #000000" >
          <h5>TIPS</h5>
          <p>
            <strong>
            1.- NO SE ESTAQUEEN EN BOTES OPEN RAISEADOS CON TOP PAR U OVER PAR <br>
            2.- RAISE AL TURN CASI SIEMPRE ES NUTS <br>
            3.- NO HAGAN SLOW PLAY CONTRA FISHES <br>
            4.- BOTES MULTIWAY LOS RANGOS SON MAS FUERTES POR CONISUGIENTE TOP PAR MEDIOS ES TRASH <br>
            5.- NO HAGAN CALL A LAS 3-bets POR DETRÁS… O 4-BETEAN O FOLDEAN <br>
            6.- NO HAGAN CALL A LAS 4-BETS O SHOVEAN O FOLDEAN GUERRA DE BLIDNS JJ+ Aks y Ako <br>
            7.- Aca donde debes nitear demasiado es en el river <br> generalmente en el river tienen muy pocos faroles y debrias foldear mucho mas de la media. <br> A menos que tengas mas de 1 razon para pagar <br>
            8.- NUNCA TE OLVIDES QUE LAS TABLAS SON GUIAS NO TE CIEGUES <br>
            9.- Por el momento no donkear bajo ninguna razon
            </strong>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
  import {Component, Vue} from "nuxt-property-decorator"
  
  @Component({})

  export default class PokerTables extends Vue {
    bbValue=false
    bbvsutgValue=true
    bbvsmpValue=false
    bbvscoValue=false
    bbvsbtnValue=false
    bbvssbValue=false

    sbValue=false
    sborValue=true
    sbvsutgValue=false
    sbvsmpValue=false
    sbvscoValue=false
    sbvsbtnValue=false

    btnValue=false
    btnorValue=true
    btnvsutgValue=false
    btnvsmpValue=false
    btnvscoValue=false

    coValue=false
    coorValue=true
    covsutgValue=false
    covsmpValue=false

    mpValue=false
    mporValue=true
    mpvsutgValue=false

    utgValue=true
    sqzValue=false
    rolValue=false

    tableView(table:any){
      if(table=='utg'){
        this.utgValue=true
        this.sqzValue=false
        this.rolValue=false
        this.sbValue=false
        this.btnValue=false
        this.coValue=false
        this.mpValue=false
        this.bbValue=false
        
      }else if (table=='sqz' ){
        this.utgValue=false
        this.sqzValue=true
        this.rolValue=false
        this.sbValue=false
        this.btnValue=false
        this.coValue=false
        this.mpValue=false
        this.bbValue=false
       
      }else if (table=='rol' ){
        this.utgValue=false
        this.sqzValue=false
        this.rolValue=true
        this.sbValue=false
        this.btnValue=false
        this.coValue=false
        this.mpValue=false
        this.bbValue=false
       
      }else if (table=='bb' ){
        this.utgValue=false
        this.sqzValue=false
        this.rolValue=false
        this.sbValue=false
        this.btnValue=false
        this.coValue=false
        this.mpValue=false
        this.bbValue=true
       
      }else if (table=='sb' ){
        this.utgValue=false
        this.sqzValue=false
        this.rolValue=false
        this.sbValue=true
        this.btnValue=false
        this.coValue=false
        this.mpValue=false
        this.bbValue=false
       
      }else if (table=='btn' ){
        this.utgValue=false
        this.sqzValue=false
        this.rolValue=false
        this.sbValue=false
        this.btnValue=true
        this.coValue=false
        this.mpValue=false
        this.bbValue=false
       
      }else if (table=='co' ){
        this.utgValue=false
        this.sqzValue=false
        this.rolValue=false
        this.sbValue=false
        this.btnValue=false
        this.coValue=true
        this.mpValue=false
        this.bbValue=false
        
      }else if (table=='mp' ){
        this.utgValue=false
        this.sqzValue=false
        this.rolValue=false
        this.sbValue=false
        this.btnValue=false
        this.coValue=false
        this.mpValue=true
        this.bbValue=false
      }
    }

    tableViewMore(tableMore:any){
      if(this.bbValue){
        if(tableMore=='bbvsutg'){
          this.bbvsutgValue=true
          this.bbvsmpValue=false
          this.bbvscoValue=false
          this.bbvsbtnValue=false
          this.bbvssbValue=false
         
        }else if (tableMore=='bbvsmp' ){
          this.bbvsutgValue=false
          this.bbvsmpValue=true
          this.bbvscoValue=false
          this.bbvsbtnValue=false
          this.bbvssbValue=false
         
        }else if (tableMore=='bbvsco' ){
          this.bbvsutgValue=false
          this.bbvsmpValue=false
          this.bbvscoValue=true
          this.bbvsbtnValue=false
          this.bbvssbValue=false
         
        }else if (tableMore=='bbvsbtn' ){
          this.bbvsutgValue=false
          this.bbvsmpValue=false
          this.bbvscoValue=false
          this.bbvsbtnValue=true
          this.bbvssbValue=false
         
        }else if (tableMore=='bbvssb' ){
          this.bbvsutgValue=false
          this.bbvsmpValue=false
          this.bbvscoValue=false
          this.bbvsbtnValue=false
          this.bbvssbValue=true
         
        }
      }else if(this.sbValue){
        if(tableMore=='sbor'){
          this.sborValue=true
          this.sbvsutgValue=false
          this.sbvsmpValue=false
          this.sbvscoValue=false
          this.sbvsbtnValue=false
        }else if (tableMore=='sbvsutg' ){
          this.sborValue=false
          this.sbvsutgValue=true
          this.sbvsmpValue=false
          this.sbvscoValue=false
          this.sbvsbtnValue=false
         
        }else if (tableMore=='sbvsmp' ){
          this.sborValue=false
          this.sbvsutgValue=false
          this.sbvsmpValue=true
          this.sbvscoValue=false
          this.sbvsbtnValue=false
         
        }else if (tableMore=='sbvsco' ){
          this.sborValue=false
          this.sbvsutgValue=false
          this.sbvsmpValue=false
          this.sbvscoValue=true
          this.sbvsbtnValue=false
         
        }else if (tableMore=='sbvsbtn' ){
          this.sborValue=false
          this.sbvsutgValue=false
          this.sbvsmpValue=false
          this.sbvscoValue=false
          this.sbvsbtnValue=true
         
        }
      }else if(this.btnValue){
        if(tableMore=='btnor'){
          this.btnorValue=true
          this.btnvsutgValue=false
          this.btnvsmpValue=false
          this.btnvscoValue=false
        }else if (tableMore=='btnvsutg' ){
          this.btnorValue=false
          this.btnvsutgValue=true
          this.btnvsmpValue=false
          this.btnvscoValue=false
        }else if (tableMore=='btnvsmp' ){
          this.btnorValue=false
          this.btnvsutgValue=false
          this.btnvsmpValue=true
          this.btnvscoValue=false
        }else if (tableMore=='btnvsco' ){
          this.btnorValue=false
          this.btnvsutgValue=false
          this.btnvsmpValue=false
          this.btnvscoValue=true
        }
      }else if(this.coValue){
        if(tableMore=='coor'){
          this.coorValue=true
          this.covsutgValue=false
          this.covsmpValue=false
        }else if(tableMore=='covsutg'){
          this.coorValue=false
          this.covsutgValue=true
          this.covsmpValue=false
        }else if(tableMore=='covsmp'){
          this.coorValue=false
          this.covsutgValue=false
          this.covsmpValue=true
        }

      }else if(this.mpValue){
        if(tableMore=='mpor'){
          this.mporValue=true
          this.mpvsutgValue=false
        }else if(tableMore=='mpvsutg'){
          this.mporValue=false
          this.mpvsutgValue=true
        }
      }
    }
  }
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  width: 80%;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}

body {
  background-image: url("~../assets/images/mountain.jpg");
  background-size: 100%;
}

.poker.tables {
  width: 100%;
  
}

.title-tables{
  border: 1px solid rgba(0,0,0,0.8);
  border-radius: 15px;
  font-size: 13px;
  padding:5px 10px;
  background-color: palegoldenrod;
  margin-bottom: 20px;
}

</style>
