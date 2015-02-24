
<html>
<head>
<link href="//maxcdn.bootstrapcdn.com/bootstrap/3.3.2/css/bootstrap.min.css" rel="stylesheet">
<title></title>
<style type="text/css">

    div, h1, h4 {  }
    .error { color: red; }
    .good { color: green; }

    img{
        display:inline;!important
    }

    .header{
        background: #b90000;
        color: #ffffff;
        padding-bottom: 15px;
    }

    .header a{
        color: white;
    }

    .header a:hover{
        text-decoration: none;
        color: silver;
    }

    #drop {
        min-height: 300px;
        width: 300px;
        border: 1px solid silver;
        padding: 0px;
        margin: auto;
        text-align: center;
    }
</style>
<script type="text/javascript" src="https://code.jquery.com/jquery-1.11.2.min.js"></script>
<!-- QRCode.js github.com/davidshimjs/qrcodejs | github.com/davidshimjs/qrcodejs/blob/master/LICENSE -->
<script type="text/javascript">
var QRCode;!function(){function a(a){this.mode=c.MODE_8BIT_BYTE,this.data=a,this.parsedData=[];for(var b=[],d=0,e=this.data.length;e>d;d++){var f=this.data.charCodeAt(d);f>65536?(b[0]=240|(1835008&f)>>>18,b[1]=128|(258048&f)>>>12,b[2]=128|(4032&f)>>>6,b[3]=128|63&f):f>2048?(b[0]=224|(61440&f)>>>12,b[1]=128|(4032&f)>>>6,b[2]=128|63&f):f>128?(b[0]=192|(1984&f)>>>6,b[1]=128|63&f):b[0]=f,this.parsedData=this.parsedData.concat(b)}this.parsedData.length!=this.data.length&&(this.parsedData.unshift(191),this.parsedData.unshift(187),this.parsedData.unshift(239))}function b(a,b){this.typeNumber=a,this.errorCorrectLevel=b,this.modules=null,this.moduleCount=0,this.dataCache=null,this.dataList=[]}function i(a,b){if(void 0==a.length)throw new Error(a.length+"/"+b);for(var c=0;c<a.length&&0==a[c];)c++;this.num=new Array(a.length-c+b);for(var d=0;d<a.length-c;d++)this.num[d]=a[d+c]}function j(a,b){this.totalCount=a,this.dataCount=b}function k(){this.buffer=[],this.length=0}function m(){return"undefined"!=typeof CanvasRenderingContext2D}function n(){var a=!1,b=navigator.userAgent;return/android/i.test(b)&&(a=!0,aMat=b.toString().match(/android ([0-9]\.[0-9])/i),aMat&&aMat[1]&&(a=parseFloat(aMat[1]))),a}function r(a,b){for(var c=1,e=s(a),f=0,g=l.length;g>=f;f++){var h=0;switch(b){case d.L:h=l[f][0];break;case d.M:h=l[f][1];break;case d.Q:h=l[f][2];break;case d.H:h=l[f][3]}if(h>=e)break;c++}if(c>l.length)throw new Error("Too long data");return c}function s(a){var b=encodeURI(a).toString().replace(/\%[0-9a-fA-F]{2}/g,"a");return b.length+(b.length!=a?3:0)}a.prototype={getLength:function(){return this.parsedData.length},write:function(a){for(var b=0,c=this.parsedData.length;c>b;b++)a.put(this.parsedData[b],8)}},b.prototype={addData:function(b){var c=new a(b);this.dataList.push(c),this.dataCache=null},isDark:function(a,b){if(0>a||this.moduleCount<=a||0>b||this.moduleCount<=b)throw new Error(a+","+b);return this.modules[a][b]},getModuleCount:function(){return this.moduleCount},make:function(){this.makeImpl(!1,this.getBestMaskPattern())},makeImpl:function(a,c){this.moduleCount=4*this.typeNumber+17,this.modules=new Array(this.moduleCount);for(var d=0;d<this.moduleCount;d++){this.modules[d]=new Array(this.moduleCount);for(var e=0;e<this.moduleCount;e++)this.modules[d][e]=null}this.setupPositionProbePattern(0,0),this.setupPositionProbePattern(this.moduleCount-7,0),this.setupPositionProbePattern(0,this.moduleCount-7),this.setupPositionAdjustPattern(),this.setupTimingPattern(),this.setupTypeInfo(a,c),this.typeNumber>=7&&this.setupTypeNumber(a),null==this.dataCache&&(this.dataCache=b.createData(this.typeNumber,this.errorCorrectLevel,this.dataList)),this.mapData(this.dataCache,c)},setupPositionProbePattern:function(a,b){for(var c=-1;7>=c;c++)if(!(-1>=a+c||this.moduleCount<=a+c))for(var d=-1;7>=d;d++)-1>=b+d||this.moduleCount<=b+d||(this.modules[a+c][b+d]=c>=0&&6>=c&&(0==d||6==d)||d>=0&&6>=d&&(0==c||6==c)||c>=2&&4>=c&&d>=2&&4>=d?!0:!1)},getBestMaskPattern:function(){for(var a=0,b=0,c=0;8>c;c++){this.makeImpl(!0,c);var d=f.getLostPoint(this);(0==c||a>d)&&(a=d,b=c)}return b},createMovieClip:function(a,b,c){var d=a.createEmptyMovieClip(b,c),e=1;this.make();for(var f=0;f<this.modules.length;f++)for(var g=f*e,h=0;h<this.modules[f].length;h++){var i=h*e,j=this.modules[f][h];j&&(d.beginFill(0,100),d.moveTo(i,g),d.lineTo(i+e,g),d.lineTo(i+e,g+e),d.lineTo(i,g+e),d.endFill())}return d},setupTimingPattern:function(){for(var a=8;a<this.moduleCount-8;a++)null==this.modules[a][6]&&(this.modules[a][6]=0==a%2);for(var b=8;b<this.moduleCount-8;b++)null==this.modules[6][b]&&(this.modules[6][b]=0==b%2)},setupPositionAdjustPattern:function(){for(var a=f.getPatternPosition(this.typeNumber),b=0;b<a.length;b++)for(var c=0;c<a.length;c++){var d=a[b],e=a[c];if(null==this.modules[d][e])for(var g=-2;2>=g;g++)for(var h=-2;2>=h;h++)this.modules[d+g][e+h]=-2==g||2==g||-2==h||2==h||0==g&&0==h?!0:!1}},setupTypeNumber:function(a){for(var b=f.getBCHTypeNumber(this.typeNumber),c=0;18>c;c++){var d=!a&&1==(1&b>>c);this.modules[Math.floor(c/3)][c%3+this.moduleCount-8-3]=d}for(var c=0;18>c;c++){var d=!a&&1==(1&b>>c);this.modules[c%3+this.moduleCount-8-3][Math.floor(c/3)]=d}},setupTypeInfo:function(a,b){for(var c=this.errorCorrectLevel<<3|b,d=f.getBCHTypeInfo(c),e=0;15>e;e++){var g=!a&&1==(1&d>>e);6>e?this.modules[e][8]=g:8>e?this.modules[e+1][8]=g:this.modules[this.moduleCount-15+e][8]=g}for(var e=0;15>e;e++){var g=!a&&1==(1&d>>e);8>e?this.modules[8][this.moduleCount-e-1]=g:9>e?this.modules[8][15-e-1+1]=g:this.modules[8][15-e-1]=g}this.modules[this.moduleCount-8][8]=!a},mapData:function(a,b){for(var c=-1,d=this.moduleCount-1,e=7,g=0,h=this.moduleCount-1;h>0;h-=2)for(6==h&&h--;;){for(var i=0;2>i;i++)if(null==this.modules[d][h-i]){var j=!1;g<a.length&&(j=1==(1&a[g]>>>e));var k=f.getMask(b,d,h-i);k&&(j=!j),this.modules[d][h-i]=j,e--,-1==e&&(g++,e=7)}if(d+=c,0>d||this.moduleCount<=d){d-=c,c=-c;break}}}},b.PAD0=236,b.PAD1=17,b.createData=function(a,c,d){for(var e=j.getRSBlocks(a,c),g=new k,h=0;h<d.length;h++){var i=d[h];g.put(i.mode,4),g.put(i.getLength(),f.getLengthInBits(i.mode,a)),i.write(g)}for(var l=0,h=0;h<e.length;h++)l+=e[h].dataCount;if(g.getLengthInBits()>8*l)throw new Error("code length overflow. ("+g.getLengthInBits()+">"+8*l+")");for(g.getLengthInBits()+4<=8*l&&g.put(0,4);0!=g.getLengthInBits()%8;)g.putBit(!1);for(;;){if(g.getLengthInBits()>=8*l)break;if(g.put(b.PAD0,8),g.getLengthInBits()>=8*l)break;g.put(b.PAD1,8)}return b.createBytes(g,e)},b.createBytes=function(a,b){for(var c=0,d=0,e=0,g=new Array(b.length),h=new Array(b.length),j=0;j<b.length;j++){var k=b[j].dataCount,l=b[j].totalCount-k;d=Math.max(d,k),e=Math.max(e,l),g[j]=new Array(k);for(var m=0;m<g[j].length;m++)g[j][m]=255&a.buffer[m+c];c+=k;var n=f.getErrorCorrectPolynomial(l),o=new i(g[j],n.getLength()-1),p=o.mod(n);h[j]=new Array(n.getLength()-1);for(var m=0;m<h[j].length;m++){var q=m+p.getLength()-h[j].length;h[j][m]=q>=0?p.get(q):0}}for(var r=0,m=0;m<b.length;m++)r+=b[m].totalCount;for(var s=new Array(r),t=0,m=0;d>m;m++)for(var j=0;j<b.length;j++)m<g[j].length&&(s[t++]=g[j][m]);for(var m=0;e>m;m++)for(var j=0;j<b.length;j++)m<h[j].length&&(s[t++]=h[j][m]);return s};for(var c={MODE_NUMBER:1,MODE_ALPHA_NUM:2,MODE_8BIT_BYTE:4,MODE_KANJI:8},d={L:1,M:0,Q:3,H:2},e={PATTERN000:0,PATTERN001:1,PATTERN010:2,PATTERN011:3,PATTERN100:4,PATTERN101:5,PATTERN110:6,PATTERN111:7},f={PATTERN_POSITION_TABLE:[[],[6,18],[6,22],[6,26],[6,30],[6,34],[6,22,38],[6,24,42],[6,26,46],[6,28,50],[6,30,54],[6,32,58],[6,34,62],[6,26,46,66],[6,26,48,70],[6,26,50,74],[6,30,54,78],[6,30,56,82],[6,30,58,86],[6,34,62,90],[6,28,50,72,94],[6,26,50,74,98],[6,30,54,78,102],[6,28,54,80,106],[6,32,58,84,110],[6,30,58,86,114],[6,34,62,90,118],[6,26,50,74,98,122],[6,30,54,78,102,126],[6,26,52,78,104,130],[6,30,56,82,108,134],[6,34,60,86,112,138],[6,30,58,86,114,142],[6,34,62,90,118,146],[6,30,54,78,102,126,150],[6,24,50,76,102,128,154],[6,28,54,80,106,132,158],[6,32,58,84,110,136,162],[6,26,54,82,110,138,166],[6,30,58,86,114,142,170]],G15:1335,G18:7973,G15_MASK:21522,getBCHTypeInfo:function(a){for(var b=a<<10;f.getBCHDigit(b)-f.getBCHDigit(f.G15)>=0;)b^=f.G15<<f.getBCHDigit(b)-f.getBCHDigit(f.G15);return(a<<10|b)^f.G15_MASK},getBCHTypeNumber:function(a){for(var b=a<<12;f.getBCHDigit(b)-f.getBCHDigit(f.G18)>=0;)b^=f.G18<<f.getBCHDigit(b)-f.getBCHDigit(f.G18);return a<<12|b},getBCHDigit:function(a){for(var b=0;0!=a;)b++,a>>>=1;return b},getPatternPosition:function(a){return f.PATTERN_POSITION_TABLE[a-1]},getMask:function(a,b,c){switch(a){case e.PATTERN000:return 0==(b+c)%2;case e.PATTERN001:return 0==b%2;case e.PATTERN010:return 0==c%3;case e.PATTERN011:return 0==(b+c)%3;case e.PATTERN100:return 0==(Math.floor(b/2)+Math.floor(c/3))%2;case e.PATTERN101:return 0==b*c%2+b*c%3;case e.PATTERN110:return 0==(b*c%2+b*c%3)%2;case e.PATTERN111:return 0==(b*c%3+(b+c)%2)%2;default:throw new Error("bad maskPattern:"+a)}},getErrorCorrectPolynomial:function(a){for(var b=new i([1],0),c=0;a>c;c++)b=b.multiply(new i([1,g.gexp(c)],0));return b},getLengthInBits:function(a,b){if(b>=1&&10>b)switch(a){case c.MODE_NUMBER:return 10;case c.MODE_ALPHA_NUM:return 9;case c.MODE_8BIT_BYTE:return 8;case c.MODE_KANJI:return 8;default:throw new Error("mode:"+a)}else if(27>b)switch(a){case c.MODE_NUMBER:return 12;case c.MODE_ALPHA_NUM:return 11;case c.MODE_8BIT_BYTE:return 16;case c.MODE_KANJI:return 10;default:throw new Error("mode:"+a)}else{if(!(41>b))throw new Error("type:"+b);switch(a){case c.MODE_NUMBER:return 14;case c.MODE_ALPHA_NUM:return 13;case c.MODE_8BIT_BYTE:return 16;case c.MODE_KANJI:return 12;default:throw new Error("mode:"+a)}}},getLostPoint:function(a){for(var b=a.getModuleCount(),c=0,d=0;b>d;d++)for(var e=0;b>e;e++){for(var f=0,g=a.isDark(d,e),h=-1;1>=h;h++)if(!(0>d+h||d+h>=b))for(var i=-1;1>=i;i++)0>e+i||e+i>=b||(0!=h||0!=i)&&g==a.isDark(d+h,e+i)&&f++;f>5&&(c+=3+f-5)}for(var d=0;b-1>d;d++)for(var e=0;b-1>e;e++){var j=0;a.isDark(d,e)&&j++,a.isDark(d+1,e)&&j++,a.isDark(d,e+1)&&j++,a.isDark(d+1,e+1)&&j++,(0==j||4==j)&&(c+=3)}for(var d=0;b>d;d++)for(var e=0;b-6>e;e++)a.isDark(d,e)&&!a.isDark(d,e+1)&&a.isDark(d,e+2)&&a.isDark(d,e+3)&&a.isDark(d,e+4)&&!a.isDark(d,e+5)&&a.isDark(d,e+6)&&(c+=40);for(var e=0;b>e;e++)for(var d=0;b-6>d;d++)a.isDark(d,e)&&!a.isDark(d+1,e)&&a.isDark(d+2,e)&&a.isDark(d+3,e)&&a.isDark(d+4,e)&&!a.isDark(d+5,e)&&a.isDark(d+6,e)&&(c+=40);for(var k=0,e=0;b>e;e++)for(var d=0;b>d;d++)a.isDark(d,e)&&k++;var l=Math.abs(100*k/b/b-50)/5;return c+=10*l}},g={glog:function(a){if(1>a)throw new Error("glog("+a+")");return g.LOG_TABLE[a]},gexp:function(a){for(;0>a;)a+=255;for(;a>=256;)a-=255;return g.EXP_TABLE[a]},EXP_TABLE:new Array(256),LOG_TABLE:new Array(256)},h=0;8>h;h++)g.EXP_TABLE[h]=1<<h;for(var h=8;256>h;h++)g.EXP_TABLE[h]=g.EXP_TABLE[h-4]^g.EXP_TABLE[h-5]^g.EXP_TABLE[h-6]^g.EXP_TABLE[h-8];for(var h=0;255>h;h++)g.LOG_TABLE[g.EXP_TABLE[h]]=h;i.prototype={get:function(a){return this.num[a]},getLength:function(){return this.num.length},multiply:function(a){for(var b=new Array(this.getLength()+a.getLength()-1),c=0;c<this.getLength();c++)for(var d=0;d<a.getLength();d++)b[c+d]^=g.gexp(g.glog(this.get(c))+g.glog(a.get(d)));return new i(b,0)},mod:function(a){if(this.getLength()-a.getLength()<0)return this;for(var b=g.glog(this.get(0))-g.glog(a.get(0)),c=new Array(this.getLength()),d=0;d<this.getLength();d++)c[d]=this.get(d);for(var d=0;d<a.getLength();d++)c[d]^=g.gexp(g.glog(a.get(d))+b);return new i(c,0).mod(a)}},j.RS_BLOCK_TABLE=[[1,26,19],[1,26,16],[1,26,13],[1,26,9],[1,44,34],[1,44,28],[1,44,22],[1,44,16],[1,70,55],[1,70,44],[2,35,17],[2,35,13],[1,100,80],[2,50,32],[2,50,24],[4,25,9],[1,134,108],[2,67,43],[2,33,15,2,34,16],[2,33,11,2,34,12],[2,86,68],[4,43,27],[4,43,19],[4,43,15],[2,98,78],[4,49,31],[2,32,14,4,33,15],[4,39,13,1,40,14],[2,121,97],[2,60,38,2,61,39],[4,40,18,2,41,19],[4,40,14,2,41,15],[2,146,116],[3,58,36,2,59,37],[4,36,16,4,37,17],[4,36,12,4,37,13],[2,86,68,2,87,69],[4,69,43,1,70,44],[6,43,19,2,44,20],[6,43,15,2,44,16],[4,101,81],[1,80,50,4,81,51],[4,50,22,4,51,23],[3,36,12,8,37,13],[2,116,92,2,117,93],[6,58,36,2,59,37],[4,46,20,6,47,21],[7,42,14,4,43,15],[4,133,107],[8,59,37,1,60,38],[8,44,20,4,45,21],[12,33,11,4,34,12],[3,145,115,1,146,116],[4,64,40,5,65,41],[11,36,16,5,37,17],[11,36,12,5,37,13],[5,109,87,1,110,88],[5,65,41,5,66,42],[5,54,24,7,55,25],[11,36,12],[5,122,98,1,123,99],[7,73,45,3,74,46],[15,43,19,2,44,20],[3,45,15,13,46,16],[1,135,107,5,136,108],[10,74,46,1,75,47],[1,50,22,15,51,23],[2,42,14,17,43,15],[5,150,120,1,151,121],[9,69,43,4,70,44],[17,50,22,1,51,23],[2,42,14,19,43,15],[3,141,113,4,142,114],[3,70,44,11,71,45],[17,47,21,4,48,22],[9,39,13,16,40,14],[3,135,107,5,136,108],[3,67,41,13,68,42],[15,54,24,5,55,25],[15,43,15,10,44,16],[4,144,116,4,145,117],[17,68,42],[17,50,22,6,51,23],[19,46,16,6,47,17],[2,139,111,7,140,112],[17,74,46],[7,54,24,16,55,25],[34,37,13],[4,151,121,5,152,122],[4,75,47,14,76,48],[11,54,24,14,55,25],[16,45,15,14,46,16],[6,147,117,4,148,118],[6,73,45,14,74,46],[11,54,24,16,55,25],[30,46,16,2,47,17],[8,132,106,4,133,107],[8,75,47,13,76,48],[7,54,24,22,55,25],[22,45,15,13,46,16],[10,142,114,2,143,115],[19,74,46,4,75,47],[28,50,22,6,51,23],[33,46,16,4,47,17],[8,152,122,4,153,123],[22,73,45,3,74,46],[8,53,23,26,54,24],[12,45,15,28,46,16],[3,147,117,10,148,118],[3,73,45,23,74,46],[4,54,24,31,55,25],[11,45,15,31,46,16],[7,146,116,7,147,117],[21,73,45,7,74,46],[1,53,23,37,54,24],[19,45,15,26,46,16],[5,145,115,10,146,116],[19,75,47,10,76,48],[15,54,24,25,55,25],[23,45,15,25,46,16],[13,145,115,3,146,116],[2,74,46,29,75,47],[42,54,24,1,55,25],[23,45,15,28,46,16],[17,145,115],[10,74,46,23,75,47],[10,54,24,35,55,25],[19,45,15,35,46,16],[17,145,115,1,146,116],[14,74,46,21,75,47],[29,54,24,19,55,25],[11,45,15,46,46,16],[13,145,115,6,146,116],[14,74,46,23,75,47],[44,54,24,7,55,25],[59,46,16,1,47,17],[12,151,121,7,152,122],[12,75,47,26,76,48],[39,54,24,14,55,25],[22,45,15,41,46,16],[6,151,121,14,152,122],[6,75,47,34,76,48],[46,54,24,10,55,25],[2,45,15,64,46,16],[17,152,122,4,153,123],[29,74,46,14,75,47],[49,54,24,10,55,25],[24,45,15,46,46,16],[4,152,122,18,153,123],[13,74,46,32,75,47],[48,54,24,14,55,25],[42,45,15,32,46,16],[20,147,117,4,148,118],[40,75,47,7,76,48],[43,54,24,22,55,25],[10,45,15,67,46,16],[19,148,118,6,149,119],[18,75,47,31,76,48],[34,54,24,34,55,25],[20,45,15,61,46,16]],j.getRSBlocks=function(a,b){var c=j.getRsBlockTable(a,b);if(void 0==c)throw new Error("bad rs block @ typeNumber:"+a+"/errorCorrectLevel:"+b);for(var d=c.length/3,e=[],f=0;d>f;f++)for(var g=c[3*f+0],h=c[3*f+1],i=c[3*f+2],k=0;g>k;k++)e.push(new j(h,i));return e},j.getRsBlockTable=function(a,b){switch(b){case d.L:return j.RS_BLOCK_TABLE[4*(a-1)+0];case d.M:return j.RS_BLOCK_TABLE[4*(a-1)+1];case d.Q:return j.RS_BLOCK_TABLE[4*(a-1)+2];case d.H:return j.RS_BLOCK_TABLE[4*(a-1)+3];default:return void 0}},k.prototype={get:function(a){var b=Math.floor(a/8);return 1==(1&this.buffer[b]>>>7-a%8)},put:function(a,b){for(var c=0;b>c;c++)this.putBit(1==(1&a>>>b-c-1))},getLengthInBits:function(){return this.length},putBit:function(a){var b=Math.floor(this.length/8);this.buffer.length<=b&&this.buffer.push(0),a&&(this.buffer[b]|=128>>>this.length%8),this.length++}};var l=[[17,14,11,7],[32,26,20,14],[53,42,32,24],[78,62,46,34],[106,84,60,44],[134,106,74,58],[154,122,86,64],[192,152,108,84],[230,180,130,98],[271,213,151,119],[321,251,177,137],[367,287,203,155],[425,331,241,177],[458,362,258,194],[520,412,292,220],[586,450,322,250],[644,504,364,280],[718,560,394,310],[792,624,442,338],[858,666,482,382],[929,711,509,403],[1003,779,565,439],[1091,857,611,461],[1171,911,661,511],[1273,997,715,535],[1367,1059,751,593],[1465,1125,805,625],[1528,1190,868,658],[1628,1264,908,698],[1732,1370,982,742],[1840,1452,1030,790],[1952,1538,1112,842],[2068,1628,1168,898],[2188,1722,1228,958],[2303,1809,1283,983],[2431,1911,1351,1051],[2563,1989,1423,1093],[2699,2099,1499,1139],[2809,2213,1579,1219],[2953,2331,1663,1273]],o=function(){var a=function(a,b){this._el=a,this._htOption=b};return a.prototype.draw=function(a){function g(a,b){var c=document.createElementNS("http://www.w3.org/2000/svg",a);for(var d in b)b.hasOwnProperty(d)&&c.setAttribute(d,b[d]);return c}var b=this._htOption,c=this._el,d=a.getModuleCount();Math.floor(b.width/d),Math.floor(b.height/d),this.clear();var h=g("svg",{viewBox:"0 0 "+String(d)+" "+String(d),width:"100%",height:"100%",fill:b.colorLight});h.setAttributeNS("http://www.w3.org/2000/xmlns/","xmlns:xlink","http://www.w3.org/1999/xlink"),c.appendChild(h),h.appendChild(g("rect",{fill:b.colorDark,width:"1",height:"1",id:"template"}));for(var i=0;d>i;i++)for(var j=0;d>j;j++)if(a.isDark(i,j)){var k=g("use",{x:String(i),y:String(j)});k.setAttributeNS("http://www.w3.org/1999/xlink","href","#template"),h.appendChild(k)}},a.prototype.clear=function(){for(;this._el.hasChildNodes();)this._el.removeChild(this._el.lastChild)},a}(),p="svg"===document.documentElement.tagName.toLowerCase(),q=p?o:m()?function(){function a(){this._elImage.src=this._elCanvas.toDataURL("image/png"),this._elImage.style.display="inline",this._elCanvas.style.display="none"}function d(a,b){var c=this;if(c._fFail=b,c._fSuccess=a,null===c._bSupportDataURI){var d=document.createElement("img"),e=function(){c._bSupportDataURI=!1,c._fFail&&_fFail.call(c)},f=function(){c._bSupportDataURI=!0,c._fSuccess&&c._fSuccess.call(c)};return d.onabort=e,d.onerror=e,d.onload=f,d.src="data:image/gif;base64,iVBORw0KGgoAAAANSUhEUgAAAAUAAAAFCAYAAACNbyblAAAAHElEQVQI12P4//8/w38GIAXDIBKE0DHxgljNBAAO9TXL0Y4OHwAAAABJRU5ErkJggg==",void 0}c._bSupportDataURI===!0&&c._fSuccess?c._fSuccess.call(c):c._bSupportDataURI===!1&&c._fFail&&c._fFail.call(c)}if(this._android&&this._android<=2.1){var b=1/window.devicePixelRatio,c=CanvasRenderingContext2D.prototype.drawImage;CanvasRenderingContext2D.prototype.drawImage=function(a,d,e,f,g,h,i,j){if("nodeName"in a&&/img/i.test(a.nodeName))for(var l=arguments.length-1;l>=1;l--)arguments[l]=arguments[l]*b;else"undefined"==typeof j&&(arguments[1]*=b,arguments[2]*=b,arguments[3]*=b,arguments[4]*=b);c.apply(this,arguments)}}var e=function(a,b){this._bIsPainted=!1,this._android=n(),this._htOption=b,this._elCanvas=document.createElement("canvas"),this._elCanvas.width=b.width,this._elCanvas.height=b.height,a.appendChild(this._elCanvas),this._el=a,this._oContext=this._elCanvas.getContext("2d"),this._bIsPainted=!1,this._elImage=document.createElement("img"),this._elImage.style.display="none",this._el.appendChild(this._elImage),this._bSupportDataURI=null};return e.prototype.draw=function(a){var b=this._elImage,c=this._oContext,d=this._htOption,e=a.getModuleCount(),f=d.width/e,g=d.height/e,h=Math.round(f),i=Math.round(g);b.style.display="none",this.clear();for(var j=0;e>j;j++)for(var k=0;e>k;k++){var l=a.isDark(j,k),m=k*f,n=j*g;c.strokeStyle=l?d.colorDark:d.colorLight,c.lineWidth=1,c.fillStyle=l?d.colorDark:d.colorLight,c.fillRect(m,n,f,g),c.strokeRect(Math.floor(m)+.5,Math.floor(n)+.5,h,i),c.strokeRect(Math.ceil(m)-.5,Math.ceil(n)-.5,h,i)}this._bIsPainted=!0},e.prototype.makeImage=function(){this._bIsPainted&&d.call(this,a)},e.prototype.isPainted=function(){return this._bIsPainted},e.prototype.clear=function(){this._oContext.clearRect(0,0,this._elCanvas.width,this._elCanvas.height),this._bIsPainted=!1},e.prototype.round=function(a){return a?Math.floor(1e3*a)/1e3:a},e}():function(){var a=function(a,b){this._el=a,this._htOption=b};return a.prototype.draw=function(a){for(var b=this._htOption,c=this._el,d=a.getModuleCount(),e=Math.floor(b.width/d),f=Math.floor(b.height/d),g=['<table style="border:0;border-collapse:collapse;">'],h=0;d>h;h++){g.push("<tr>");for(var i=0;d>i;i++)g.push('<td style="border:0;border-collapse:collapse;padding:0;margin:0;width:'+e+"px;height:"+f+"px;background-color:"+(a.isDark(h,i)?b.colorDark:b.colorLight)+';"></td>');g.push("</tr>")}g.push("</table>"),c.innerHTML=g.join("");var j=c.childNodes[0],k=(b.width-j.offsetWidth)/2,l=(b.height-j.offsetHeight)/2;k>0&&l>0&&(j.style.margin=l+"px "+k+"px")},a.prototype.clear=function(){this._el.innerHTML=""},a}();QRCode=function(a,b){if(this._htOption={width:256,height:256,typeNumber:4,colorDark:"#000000",colorLight:"#ffffff",correctLevel:d.H},"string"==typeof b&&(b={text:b}),b)for(var c in b)this._htOption[c]=b[c];"string"==typeof a&&(a=document.getElementById(a)),this._android=n(),this._el=a,this._oQRCode=null,this._oDrawing=new q(this._el,this._htOption),this._htOption.text&&this.makeCode(this._htOption.text)},QRCode.prototype.makeCode=function(a){this._oQRCode=new b(r(a,this._htOption.correctLevel),this._htOption.correctLevel),this._oQRCode.addData(a),this._oQRCode.make(),this._el.title=a,this._oDrawing.draw(this._oQRCode),this.makeImage()},QRCode.prototype.makeImage=function(){"function"==typeof this._oDrawing.makeImage&&(!this._android||this._android>=3)&&this._oDrawing.makeImage()},QRCode.prototype.clear=function(){this._oDrawing.clear()},QRCode.CorrectLevel=d}();
</script>

<script src="//maxcdn.bootstrapcdn.com/bootstrap/3.3.2/js/bootstrap.min.js"></script>
<!-- BigInteger.js github.com/peterolson/BigInteger.js | github.com/peterolson/BigInteger.js/blob/master/LICENSE -->
<script type="text/javascript">
"use strict";var bigInt=function(){function i(e,t){this.value=e,this.sign=t}function s(e){while(e[e.length-1]===0&&e.length>1)e.pop();return e}function o(t,n){var r=n<0;if(t.sign!==r)return r?u(t.abs(),-n):u(t.abs(),n).negate();r&&(n=-n);var o=t.value,a=[],f=0;for(var l=0;l<o.length||f>0;l++){var c=(o[l]||0)+(l>0?0:n)+f;f=c>=e?1:0,a.push(c%e)}return new i(s(a),t.sign)}function u(t,n){var r=t.value;if(r.length===1)return r=r[0],t.sign&&(r=-r),new i([Math.abs(r-n)],r-n<0);if(t.sign!==n<0)return o(t,-n);var u=!1;t.sign&&(u=!0);if(r.length===1&&r[0]<n)return new i([n-r[0]],!u);u&&(n=-n);var a=[],f=0;for(var l=0;l<r.length;l++){var c=r[l]-f-(l>0?0:n);f=c<0?1:0,a.push(f*e+c)}return new i(s(a),u)}function a(t,n){var r=[],i=0;for(var s=0;s<t.length;s++){i+=n*t[s];var o=Math.floor(i/e);r[s]=i-o*e|0,i=o}return r[t.length]=i|0,r}function f(e,t){var n=a(e.value,t<0?-t:t);return new i(s(n),t<0?!e.sign:e.sign)}function l(t,n){var r=[];for(var i=0;i<t.length;i++)r[i]=0;var s=0;for(var i=t.length-1;i>=0;i--){var o=s*e+t[i],u=Math.floor(o/n);s=o-u*n,r[i]=u|0}return{quotient:r,remainder:s|0}}function c(e,t){if(t===0)throw new Error("Cannot divide by zero.");var n=l(e.value,t<0?-t:t);return{quotient:new i(s(n.quotient),t<0?!e.sign:e.sign),remainder:new i([n.remainder],e.sign)}}function h(t){return(typeof t=="number"||typeof t=="string")&&+Math.abs(t)<=e||t instanceof i&&t.value.length<=1}function p(e,t){return e=N(e).abs(),t=N(t).abs(),e.equals(t)?e:e.equals(S)?t:t.equals(S)?e:e.isEven()?t.isOdd()?p(e.divide(2),t):p(e.divide(2),t.divide(2)).multiply(2):t.isEven()?p(e,t.divide(2)):e.greater(t)?p(e.subtract(t).divide(2),t):p(t.subtract(e).divide(2),e)}function d(e,t){return e=N(e).abs(),t=N(t).abs(),e.multiply(t).divide(p(e,t))}function v(e,t){return e=N(e),t=N(t),e.greater(t)?e:t}function m(e,t){return e=N(e),t=N(t),e.lesser(t)?e:t}function g(t,n){t=N(t),n=N(n);var r=m(t,n),s=v(t,n),o=s.subtract(r),u=o.value.length-1,a=[],f=!0;for(var l=u;l>=0;l--){var c=f?o.value[l]:e,h=Math.floor(Math.random()*c);a.unshift(h),h<c&&(f=!1)}return r.add(new i(a,!1))}function E(e,t,n){var r=S,i=v(e.abs(),t.abs()),s=0,o=x;while(o.lesserOrEquals(i)){var u,a;u=e.over(o).isEven()?0:1,a=t.over(o).isEven()?0:1,r=r.add(o.times(n(u,a))),o=f(o,2)}return r}function N(n){if(n instanceof i)return n;if(Math.abs(+n)<e&&+n===(+n|0)){var o=+n;return new i([Math.abs(o)],o<0||1/o===-Infinity)}n+="";var u=r.positive,o=[];n[0]==="-"&&(u=r.negative,n=n.slice(1));var n=n.split(/e/i);if(n.length>2)throw new Error("Invalid integer: "+n.join("e"));if(n[1]){var a=n[1];a[0]==="+"&&(a=a.slice(1)),a=N(a);var f=n[0].indexOf(".");f>=0&&(a=a.minus(n[0].length-f),n[0]=n[0].slice(0,f)+n[0].slice(f+1));if(a.lesser(0))throw new Error("Cannot include negative exponent part for integers");while(a.notEquals(0))n[0]+="0",a=a.prev()}n=n[0],n==="-0"&&(n="0");var l=/^([0-9][0-9]*)$/.test(n);if(!l)throw new Error("Invalid integer: "+n);while(n.length){var c=n.length>t?n.length-t:0;o.push(+n.slice(c)),n=n.slice(0,c)}return new i(s(o),u)}function k(e){var t=e.value;return t.length===1&&t[0]<=36?"0123456789abcdefghijklmnopqrstuvwxyz".charAt(t[0]):"<"+t+">"}function L(e,t){t=bigInt(t);if(t.equals(0)){if(e.equals(0))return"0";throw new Error("Cannot convert nonzero numbers to base 0.")}if(t.equals(-1))return e.equals(0)?"0":e.lesser(0)?Array(1-e).join("10"):"1"+Array(+e).join("01");var n="";e.isNegative()&&t.isPositive()&&(n="-",e=e.abs());if(t.equals(1))return e.equals(0)?"0":n+Array(+e+1).join(1);var r=[],i=e,s;while(i.lesser(0)||i.compareAbs(t)>=0){s=i.divmod(t),i=s.quotient;var o=s.remainder;o.lesser(0)&&(o=t.minus(o).abs(),i=i.next()),r.push(k(o))}return r.push(k(i)),n+r.reverse().join("")}var e=1e7,t=7,n="0000000",r={positive:!1,negative:!0};i.prototype.negate=function(){return new i(this.value,!this.sign)},i.prototype.abs=function(){return new i(this.value,r.positive)},i.prototype.add=function(t){if(h(t))return o(this,+t);t=N(t);if(this.sign!==t.sign)return this.sign===r.positive?this.abs().subtract(t.abs()):t.abs().subtract(this.abs());var n=this.value,u=t.value,a=[],f=0,l=Math.max(n.length,u.length);for(var c=0;c<l||f>0;c++){var p=(n[c]||0)+(u[c]||0)+f;f=p>=e?1:0,a.push(p%e)}return new i(s(a),this.sign)},i.prototype.plus=i.prototype.add,i.prototype.subtract=function(t){if(h(t))return u(this,+t);t=N(t);if(this.sign!==t.sign)return this.add(t.negate());if(this.sign===r.negative)return t.negate().subtract(this.negate());if(this.compare(t)<0)return t.subtract(this).negate();var n=this.value,o=t.value,a=[],f=0,l=Math.max(n.length,o.length);for(var c=0;c<l;c++){var p=n[c]||0,d=o[c]||0,v=p-f;f=v<d?1:0,a.push(f*e+v-d)}return new i(s(a),r.positive)},i.prototype.minus=i.prototype.subtract,i.prototype.multiply=function(t){if(h(t))return f(this,+t);t=N(t);var n=this.sign!==t.sign,r=this.value,o=t.value,u=[];for(var a=r.length+o.length;a>0;a--)u.push(0);for(var a=0;a<r.length;a++){var l=r[a];for(var c=0;c<o.length;c++){var p=o[c],d=l*p+u[a+c],v=Math.floor(d/e);u[a+c]=d-v*e,u[a+c+1]+=v}}return new i(s(u),n)},i.prototype.times=i.prototype.multiply,i.prototype.divmod=function(t){if(h(t))return c(this,+t);t=N(t);var n=this.sign!==t.sign;if(t.equals(S))throw new Error("Cannot divide by zero");if(this.equals(S))return{quotient:new i([0],r.positive),remainder:new i([0],r.positive)};var o=this.value,u=t.value,f=[0];for(var p=0;p<u.length;p++)f[p]=0;var d=u[u.length-1],v=Math.ceil(e/2/d),m=a(o,v),g=a(u,v);d=g[u.length-1];for(var y=o.length-u.length;y>=0;y--){var b=e-1;m[y+u.length]!==d&&(b=Math.floor((m[y+u.length]*e+m[y+u.length-1])/d));var w=0,E=0;for(var p=0;p<g.length;p++){w+=b*g[p];var x=Math.floor(w/e);E+=m[y+p]-(w-x*e),w=x,E<0?(m[y+p]=E+e|0,E=-1):(m[y+p]=E|0,E=0)}while(E!==0){b-=1;var w=0;for(var p=0;p<g.length;p++)w+=m[y+p]-e+g[p],w<0?(m[y+p]=w+e|0,w=0):(m[y+p]=w|0,w=1);E+=w}f[y]=b|0}return m=l(m,v).quotient,{quotient:new i(s(f),n),remainder:new i(s(m),this.sign)}},i.prototype.divide=function(e){return this.divmod(e).quotient},i.prototype.over=i.prototype.divide,i.prototype.mod=function(e){return this.divmod(e).remainder},i.prototype.remainder=i.prototype.mod,i.prototype.pow=function(e){e=N(e);var t=this,n=e,r=x;if(n.equals(S))return r;if(t.equals(S)||n.lesser(S))return S;for(;;){n.isOdd()&&(r=r.times(t)),n=n.divide(2);if(n.equals(S))break;t=t.times(t)}return r},i.prototype.modPow=function(e,t){e=N(e),t=N(t);if(t.equals(S))throw new Error("Cannot take modPow with modulus 0");var n=x,r=this.mod(t);if(r.equals(S))return S;while(e.greater(0))e.isOdd()&&(n=n.multiply(r).mod(t)),e=e.divide(2),r=r.square().mod(t);return n},i.prototype.square=function(){return this.multiply(this)},i.prototype.next=function(){return o(this,1)},i.prototype.prev=function(){return u(this,1)},i.prototype.compare=function(e){var t=this,n=N(e);if(t.value.length===1&&n.value.length===1&&t.value[0]===0&&n.value[0]===0)return 0;if(n.sign!==t.sign)return t.sign===r.positive?1:-1;var i=t.sign===r.positive?1:-1,s=t.value,o=n.value,u=Math.max(s.length,o.length)-1;for(var a=u;a>=0;a--){var f=s[a]||0,l=o[a]||0;if(f>l)return 1*i;if(l>f)return-1*i}return 0},i.prototype.compareAbs=function(e){return this.abs().compare(e.abs())},i.prototype.equals=function(e){return this.compare(e)===0},i.prototype.notEquals=function(e){return!this.equals(e)},i.prototype.lesser=function(e){return this.compare(e)<0},i.prototype.greater=function(e){return this.compare(e)>0},i.prototype.greaterOrEquals=function(e){return this.compare(e)>=0},i.prototype.lesserOrEquals=function(e){return this.compare(e)<=0},i.prototype.compareTo=i.prototype.compare,i.prototype.lt=i.prototype.lesser,i.prototype.leq=i.prototype.lesserOrEquals,i.prototype.gt=i.prototype.greater,i.prototype.geq=i.prototype.greaterOrEquals,i.prototype.eq=i.prototype.equals,i.prototype.neq=i.prototype.notEquals,i.prototype.isPositive=function(){return this.value.length===1&&this.value[0]===0?!1:this.sign===r.positive},i.prototype.isNegative=function(){return this.value.length===1&&this.value[0]===0?!1:this.sign===r.negative},i.prototype.isEven=function(){return this.value[0]%2===0},i.prototype.isOdd=function(){return this.value[0]%2===1},i.prototype.isUnit=function(){return this.value.length===1&&this.value[0]===1},i.prototype.isZero=function(){return this.value.length===1&&this.value[0]===0},i.prototype.isDivisibleBy=function(e){return e=N(e),e.isZero()?!1:this.mod(e).equals(S)},i.prototype.isPrime=function(){var e=this.abs(),t=e.prev();if(e.isUnit())return!1;if(e.equals(2)||e.equals(3)||e.equals(5))return!0;if(e.isEven()||e.isDivisibleBy(3)||e.isDivisibleBy(5))return!1;if(e.lesser(25))return!0;var n=[2,3,5,7,11,13,17,19],r=t,i,s,o,u;while(r.isEven())r=r.divide(2);for(o=0;o<n.length;o++){u=bigInt(n[o]).modPow(r,e);if(u.equals(x)||u.equals(t))continue;for(s=!0,i=r;s&&i.lesser(t);i=i.multiply(2))u=u.square().mod(e),u.equals(t)&&(s=!1);if(s)return!1}return!0};var y=[1];while(y[y.length-1]<=e)y.push(2*y[y.length-1]);var b=y.length,w=y[b-1];i.prototype.shiftLeft=function(e){if(!h(e))return e.isNegative()?this.shiftRight(e.abs()):this.times(bigInt(2).pow(e));e=+e;if(e<0)return this.shiftRight(-e);var t=this;while(e>=b)t=f(t,w),e-=b-1;return f(t,y[e])},i.prototype.shiftRight=function(e){if(!h(e))return e.isNegative()?this.shiftLeft(e.abs()):this.over(bigInt(2).pow(e));e=+e;if(e<0)return this.shiftLeft(-e);var t=this;while(e>=b){if(t.equals(S))return t;t=c(t,w).quotient,e-=b-1}return c(t,y[e]).quotient},i.prototype.not=function(){var e=E(this,this,function(e){return(e+1)%2});return this.sign?e:e.negate()},i.prototype.and=function(e){e=N(e);var t=E(this,e,function(e,t){return e*t});return this.sign&&e.sign?t.negate():t},i.prototype.or=function(e){e=N(e);var t=E(this,e,function(e,t){return(e+t+e*t)%2});return this.sign||e.sign?t.negate():t},i.prototype.xor=function(e){e=N(e);var t=E(this,e,function(e,t){return(e+t)%2});return this.sign^e.sign?t.negate():t},i.prototype.toString=function(e){e===undefined&&(e=10);if(e!==10)return L(this,e);var t=this,i="",s=t.value.length;if(s===0||s===1&&t.value[0]===0)return"0";s-=1,i=t.value[s].toString();while(--s>=0){var o=t.value[s].toString();i+=n.slice(o.length)+o}var u=t.sign===r.positive?"":"-";return u+i},i.prototype.toJSNumber=function(){return this.valueOf()},i.prototype.valueOf=function(){return this.value.length===1?this.sign?-this.value[0]:this.value[0]:+this.toString()};var S=new i([0],r.positive),x=new i([1],r.positive),T=new i([1],r.negative),C=function(e,t){function o(e){var t=e[i].toLowerCase();if(i===0&&e[i]==="-"){s=!0;return}if(/[0-9]/.test(t))r.push(N(t));else if(/[a-z]/.test(t))r.push(N(t.charCodeAt(0)-87));else{if(t!=="<")throw new Error(t+" is not a valid character");var n=i;do i++;while(e[i]!==">");r.push(N(e.slice(n+1,i)))}}t=N(t);var n=S,r=[],i,s=!1;for(i=0;i<e.length;i++)o(e);r.reverse();for(i=0;i<r.length;i++)n=n.add(r[i].times(t.pow(i)));return s?n.negate():n},A=function(e,t){return typeof e=="undefined"?S:typeof t!="undefined"?C(e,t):N(e)};return A.zero=S,A.one=x,A.minusOne=T,A.randBetween=g,A.min=m,A.max=v,A.gcd=p,A.lcm=d,A}();typeof module!="undefined"&&(module.exports=bigInt);
</script>
<script type="text/javascript">

if (window.FileReader) {

    addEventHandler(window, 'load', function () {

        $("img").bind("load",function(){
            $(this).removeAttr("style");
        });

        var status = document.getElementById('status');
        var drop = document.getElementById('drop');
        var server = document.getElementById('server');
        var filename = document.getElementById('filename');

        qrcode = new QRCode(drop, {
            text: "",
            width: 300,
            height: 300,
            colorDark : "#000000",
            colorLight : "#ffffff",
            correctLevel : QRCode.CorrectLevel.L
        });

        function cancel(e) {
            if (e.preventDefault) {
                e.preventDefault();
            }
            return false;
        }

        function dropfunc(e) {
            e = e || window.event;
            cancel(e);
            qrcode.clear();

            var dt = e.dataTransfer;
            var files = dt.files;

            if(files.length == 0) {
                return false;
            }

            if(files.length > 1) {
                status.className = 'error';
                status.innerHTML = 'Drag only one file';
                return false;
            }

            var file = files[0];
            
            if(file.size != 232 && file.size != 260 && file.size != 264) {
                status.className = 'error';
                status.innerHTML = 'Invalid file size';
                return false;
            }

            var reader = new FileReader();
            reader.readAsBinaryString(file);

            addEventHandler(reader, 'loadend', function (e) {
                    
                var contents = e.target.result,
                    error    = e.target.error;

                if (error != null) {
                    status.className = 'error text-center';
                    status.innerHTML = 'File could not be read! ['+ error.code + ']';
                    return false;
                }

                if (file.size == 232 || file.size == 260) try {
                    contents = checkPkx(contents.substring(0, 232));
                } catch(e) {
                    status.className = 'error text-center';
                    status.innerHTML = e.message;
                    return false;
                }

                try {
                    qrcode.makeCode(server.value + btoa(contents));
                    status.className = 'good text-center';
                    status.innerHTML = "Scan the QR code to begin injecting!";
                    filename.className = 'good text-center';
                    filename.innerHTML = file.name;
                } catch(e) {
                    status.className = 'error text-center';
                    status.innerHTML = "Error generating QR code (too big?)";
                }

            });

            return false;
        }

        addEventHandler(document.body, 'dragover', cancel);
        addEventHandler(document.body, 'dragenter', cancel);
        addEventHandler(document.body, 'drop', dropfunc);
    });

} else {
    document.getElementById('status').innerHTML = 'Your browser is not compatible';
}

function addEventHandler(obj, evt, handler) {
    if (obj.addEventListener) {
        obj.addEventListener(evt, handler, false);
    } else if (obj.attachEvent) {
        obj.attachEvent('on' + evt, handler);
    } else {
        obj['on' + evt] = handler;
    }
}

var A = 0, B = 1, C = 2, D = 3;

var blocks = [
            /*   enc   */  /*   dec   */
/* 00 */    [[A, B, C, D], [A, B, C, D]],
/* 01 */    [[A, B, D, C], [A, B, D, C]],
/* 02 */    [[A, C, B, D], [A, C, B, D]],
/* 03 */    [[A, C, D, B], [A, D, B, C]],
/* 04 */    [[A, D, B, C], [A, C, D, B]],
/* 05 */    [[A, D, C, B], [A, D, C, B]],
/* 06 */    [[B, A, C, D], [B, A, C, D]],
/* 07 */    [[B, A, D, C], [B, A, D, C]],
/* 08 */    [[B, C, A, D], [C, A, B, D]],
/* 09 */    [[B, C, D, A], [D, A, B, C]],
/* 10 */    [[B, D, A, C], [C, A, D, B]],
/* 11 */    [[B, D, C, A], [D, A, C, B]],
/* 12 */    [[C, A, B, D], [B, C, A, D]],
/* 13 */    [[C, A, D, B], [B, D, A, C]],
/* 14 */    [[C, B, A, D], [C, B, A, D]],
/* 15 */    [[C, B, D, A], [D, B, A, C]],
/* 16 */    [[C, D, A, B], [C, D, A, B]],
/* 17 */    [[C, D, B, A], [D, C, A, B]],
/* 18 */    [[D, A, B, C], [B, C, D, A]],
/* 19 */    [[D, A, C, B], [B, D, C, A]],
/* 20 */    [[D, B, A, C], [C, B, D, A]],
/* 21 */    [[D, B, C, A], [D, B, C, A]],
/* 22 */    [[D, C, A, B], [C, D, B, A]],
/* 23 */    [[D, C, B, A], [D, C, B, A]]
];

function nextRandom(obj) {
    obj.seed = obj.seed.multiply(0x41C64E6D).add(0x00006073).and(0xFFFFFFFF);
    return obj.seed >>> 16;
}

function valChk(pk) {
    var sum = 0;

    var chk = pk[6] + ( pk[7] << 8 );

    for(var i = 8; i < 232; i+=2) {
        sum = ( sum + ( pk[i] + ( pk[i+1] << 8 ) ) ) & 0xFFFFFFFF;
    }
    sum &= 0xFFFF;

    return sum === chk;
}

function cipherPkx(pk) {
    var aux = 0;
    var seed = {};

    seed.seed = bigInt(pk[0] + (pk[1] << 8) + (pk[2] << 16) + (pk[3] * 0x1000000));

    for(var i = 8; i < 232; i+=2) {
        aux = (pk[i] + ( pk[i+1] << 8 )) ^ nextRandom(seed);
        pk[i] = aux & 0xFF;
        pk[i+1] = aux >>> 8;
    }
}

function shuffleBlocks(pk, mode) {
    var aux = [];
    var order;

    for(var i = 0; i < 232; ++i)
        aux[i] = pk[i];

    order = (((pk[0] + (pk[1] << 8) + (pk[2] << 16) ) & 0x3E000) >>> 0xD) % 24;

    for(var i = 0; i < 4; ++i)
        for(var j = 0; j < 56; ++j)
            pk[j + 56 * i + 8] = aux[j + 56 * blocks[order][mode][i] + 8];
}

function encryptPkx(pkx) {
    shuffleBlocks(pkx, 0);
    cipherPkx(pkx);
}

function decryptPkx(pkx) {
    cipherPkx(pkx);
    shuffleBlocks(pkx, 1);
}

function checkPkx(str) {

    var pk = [];

    for(var i = 0, j = 0; i < str.length;)
        pk[i++] = str.charCodeAt(j++) & 0xFF;

    if(!valChk(pk)) {
        decryptPkx(pk);
        if(!valChk(pk))
            throw new Error("BAD CHECKSUM");
    }
    encryptPkx(pk);
    return String.fromCharCode.apply(null, pk);
}

</script>
</head>
<body>
    <div class="container-fluid header">
        <div class="row">
            <div class="col-xs-12 col-sm-12 col-md-12 col-lg-12">
                <h1 class="text-center">Pokemon Injector&nbsp;<small><a href="http://www.reddit.com/r/PokemonQRCodes/">r/PokemonQRCodes</a></small></h1>
                <div>
                    <input size=28 name="server" type="hidden" id="server" value="http://okushama.github.io/b1s1.html#">
                </div>
            </div>
        </div>
    </div>
    <div class="container">
        <div class="row">
            <div class="hidden-xs hidden-sm col-md-6 col-lg-6">
            <h3>Instructions:</h3>
            <p>Follow these steps and you'll have all the Pokemon you need in no time!</p>
            <br>
            <h4>To generate the QR Code</h4>
            <ol>
            <li>Drag and Drop any <code>ekx/ek6/pkx/pk6</code> file onto <strong>anywhere</strong> on this window</li>
            <li>Grab your 3DS to do the rest</li>
            </ol>

            <p><em>Use PKHeX to create these files, Grab it for <a href="http://projectpokemon.org/forums/showthread.php?36986-PKHeX-%28Gen-6-SAV-PKX-Editor%29">PC</a> or <a href="https://docs.google.com/uc?id=0By1gvGT83A7UMzNrYmVXeENwZGs&export=download">MAC</a> .</em></p>
            <br>
            <h4>To Inject the Pokemon</h4>
            <p>You will need a <code>2DS/3DS/3DSXL</code> running firmware <code>9.0-9.5</code> and a copy of <code>X/Y/OR/AS</code><br>
            <em>(Note: 'New 3DS' and 'New 3DSXL' are incompatible with this exploit)</em></p>
            <ol>
            <li>Make sure you have an empty slot in the first space of your first box</li>
            <li>Press the 3DS Home button to access the overlay</li>
            <li>Press L and R together to open the camera</li>
            <li>Switch to QR Reading mode</li>
            <li>Scan the QR code generated on this page</li>
            <li>Allow the page to open</li>
            <li>Wait for Browser to stop working</li>
            <li>Press the 3DS Home button to return to the game</li>
            </ol>

            <h5>Your first box's first slot now has the Pokemon from the file!<br>
            <small><em>If you perform the exploit whilst viewing the first box switch boxes to make the pokemon render correctly</em></small></h5>
            </p>
            </div>

            <div class="hidden-xs col-sm-12 col-md-6 col-lg-6">
                <h4 id="status" class="text-center" style="margin-top:25px">Your QR code will generate here!</h4>
                <div id="drop"></div>
                <h4 id="filename" class="text-center"></h4>
            </div>
            <div class="visible-xs col-xs-12">
            <h1>Please visit this page on a larger device</h1>
            </div>
        </div>
    </div>
</body>
</html>
