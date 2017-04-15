
---

#### 000

@@@
{
    "title": "demo",
    "author": "ushio",
    "description": "test"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

#define PI 3.14159265359

vec3 hsv(float h, float s, float v){
    vec4 t = vec4(1.0, 2.0 / 3.0, 1.0 / 3.0, 3.0);
    vec3 p = abs(fract(vec3(h) + t.xyz) * 6.0 - vec3(t.w));
    return v * mix(vec3(t.x), clamp(p - vec3(t.x), 0.0, 1.0), s);
}

void main(){
    // -1 ~ 1 正規化座標系
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / min(resolution.x, resolution.y);
    // vec4 color = vec4(vec3(sin(length(p) * 50.0)), 1.0);
    // vec4 color = vec4(vec3(length(p)), 1.0);
    
    float theta = atan(p.y, p.x) / PI;
    float v = fract(time + theta * 10.0 + length(p) * 4.0);
    // float theta = (atan(p.y, p.x) + PI ) / (PI * 2.0);
    gl_FragColor = vec4(vec3(v), 1.0);
    
    // vec4 color = vec4(p.x);
    // vec4 color = vec4(fract(p * 10.0), 1.0, 1.0);
    // gl_FragColor = color;
    
    // if(p.y + sin(time) > 0.0) {
    // 	gl_FragColor = vec4(1.0, 1.0, 1.0, 1.0);
    // } else {
    // 	gl_FragColor = vec4(0.0, 1.0, 1.0, 1.0);
    // }
    
    
    /*
    vec2 p = gl_FragCoord.xy / resolution;
    
    
    float v1 = mod(floor(sin((gl_FragCoord.x + time * 100.0) * 0.05) + cos(gl_FragCoord.y * 0.05)), 2.0);
    vec4 color = vec4(vec3(v1), 1.0);
    gl_FragColor = color;
    vec4 backcolor = texture2D(backbuffer, gl_FragCoord.xy / min(resolution.x, resolution.y));
    */
}

|||

---


#### 000

@@@
{
    "title": "plasma noise",
    "author": "ushio",
    "description": "plasma noise"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

 
float plasma(vec2 p)
{
  p *= 20.0;
  return (sin(p.x)*0.25+0.25) + (sin(p.y)*0.25+0.25);
}

void main() {
  vec2 pos = (gl_FragCoord.xy * 2.0 - resolution) / resolution.y;
 
 pos.y += sin(gl_FragCoord.x * 0.01 * sin(time));
 pos.x += sin(gl_FragCoord.y * 0.01 * sin(time));
 
  gl_FragColor = vec4(plasma(pos));
  gl_FragColor.a = 1.0;
}
|||

---


#### 000

@@@
{
    "title": "チカチカ",
    "author": "koi_zoom1",
    "description": "チカチカするデモです"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

void main(){
    vec2 pos = (gl_FragCoord.xy * 2.0 -resolution) / resolution.y;
    gl_FragColor = vec4(vec3(mod(gl_FragCoord.x ,length(pos+sin(time)))),1.0);
    gl_FragColor /= vec4(vec3(mod(gl_FragCoord.y,length(pos+sin(time)))),1.0);
    gl_FragColor.xyz *= vec3(cos(time)+pos.x,sin(time)+pos.y,1.0);
}
|||

---


#### 000

@@@
{
    "title": "光る球",
    "author": "diwao",
    "description": "マウス位置と時間経過で色が変化"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

// vec3 get_color() {
// 	return vec3(sin(time) * 3.0, sin(time) * 4.0, sin(time) * 5.0);
// }

vec3 get_color() {
    return vec3(mouse.yx, sin(time));
}

void main() {
    vec2 p = (gl_FragCoord.xy *2.0 - resolution) / resolution.y;
    float f = 0.1 / length(p);
    gl_FragColor = vec4(vec3(f), 1.0);
    if (gl_FragCoord.x > 0.0) {
        gl_FragColor *= vec4(get_color(), 1.0);
    }
}
|||

---


#### 000

@@@
{
    "title": "ぐにゃぐにゃ",
    "author": "y_kogawa",
    "description": "中央の発光体の輪郭がとろけてる感じ"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)

void main(void){
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / min(resolution.x, resolution.y);
    vec3 color = vec3(0.0, 0.0, 0.0);
    for(float i = 0.0; i < 6.0; i++){
        float j = i + 1.0;
        vec2 q = p + vec2(cos(time * j) * 0.5, sin(time * j) * 0.5) * 0.4;
        color += 0.06 / length(q);
    }
    gl_FragColor = vec4(color, 1.0);
}

|||

---


#### 000

@@@
{
    "title": "dance floor!",
    "author": "doxas",
    "description": "まるでダンスフロアのような？"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

vec3 hsv(float h, float s, float v){
    vec4 t = vec4(1.0, 2.0 / 3.0, 1.0 / 3.0, 3.0);
    vec3 p = abs(fract(vec3(h) + t.xyz) * 6.0 - vec3(t.w));
    return v * mix(vec3(t.x), clamp(p - vec3(t.x), 0.0, 1.0), s);
}

void main(){
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / min(resolution.x, resolution.y);
    vec3 color = vec3(0.0);
    for(int i = 0; i < 10; ++i){
    	float s = sin(time * float(i) * 0.2) * 0.4 * cos(time);
    	float c = cos(time * float(i) * 0.5) * 0.5 * sin(time);
    	vec2 q = mat2(c, s, -s, c) * (p + vec2(s, c));
        float r = 0.01 / length(q);
        float g = 0.02 / length(q);
        float b = 0.03 / length(q);
        color += vec3(r, g, b) * hsv(float(i) * sin(time), 1.0, 0.2);
    }
    gl_FragColor = vec4(color, 1.0);
}

|||

---


#### 000

@@@
{
    "title": "暗黒世界",
    "author": "tanshio",
    "description": "霞かかった感じになりました"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

#define MULT   10.0
#define MULT_A 20.0
#define MULT_B 20.0

vec4 get_color(vec2 p) {
    return vec4(sin(length(p * p * p) * 5.0 + time));
}


float map(vec3 p) {
    return length(mod(p, 2.0) - 1.0) - 0.1;
}

float rand(vec2 co){
    return fract(sin(dot(co.xy ,vec2(12.9898,78.233))) * 43758.5453);
}

void main() {
    vec2 uv = (gl_FragCoord.xy * 2.0 - resolution) / resolution.y;
    vec3 pos = vec3(sin(time), rand(uv), time); //xyz
    vec3 dir = normalize(vec3(uv, 1.0));
    float t = 0.0;
    for(int i = 0; i < 10;i++) {
    	vec3 temp = pos + dir * t;
    	t += map(temp);
    }
    gl_FragColor.xyz = vec3(t * 0.05);
    // gl_FragColor.xyz += vec3(sin(time) + 0.5)
    
    gl_FragColor.a = 1.0;
}
|||

---


#### 000

@@@
{
    "title": "転がるドラ○もん",
    "author": "koi_zoom1",
    "description": "ドラえ○んが転がります！"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

#define wh vec3(1.0)
#define bl vec3(0.0)
#define re vec3(1.0, 0.0, 0.0)
#define or vec3(0.8, 0.2, 0.0)
#define be vec3(0.2, 0.5, 1.0)

void ci(vec2 p, vec2 of, float si, vec3 cl, inout vec3 i){
    float l=length(p - of);
    if(l < si){i=cl;}
    
}

void rect(vec2 p, vec2 of, float si, vec3 cl, inout vec3 i){
    vec2 q=(p - of) / si;
    if(abs(q.x) < 1.0 && abs(q.y) < 1.0){
        i=cl;
        
    }
    
}

void ell(vec2 p, vec2 of, vec2 prop, float si, vec3 cl, inout vec3 i){
    vec2 q=(p - of) / prop;
    if(length(q) < si){
        i=cl;
        
    }
}

void li(vec2 p, vec2 of, vec2 v,float si, vec3 cl, inout vec3 i){
    vec2 q=(p - of) / si;
    if(abs(q.x) < v.x && abs(q.y)< v.y){
        i=cl;
    }
}

void sl(bool flg, vec2 p, vec2 of, vec2 v,float si, vec3 cl, inout vec3 i){
    float s=sin(0.15);
    float c=cos(sin(2.0));
    vec2 q;
    if(flg==true){
        q=((p * mat2(c, -s, s, c)) - of) / si;
    }else{
        q=((p * mat2(-c, -s, -s, c)) - of) / si;
        
    }
    if(abs(q.x) < v.x && abs(q.y)< v.y){
        i=cl;
        
    }
    
}

vec2 rot(vec2 p,float a){
    float c = cos(a);
    float s = sin(a);
    return vec2(
        c * p.x - s * p.y,
        s * p.x + c * p.y
        );
}

void main(void){
    vec3 dCol=wh;
    vec2 p=(gl_FragCoord.xy * 2.0 - resolution) / 
    min(resolution.x, resolution.y);
    p = rot(p,time*1.0);;
    p.x +=cos(time*2.0)*0.5;
    p.y +=sin(time*2.0)*0.5;
    ci (p, vec2( 0.0, 0.0), 0.81, bl, dCol);
    ci (p, vec2( 0.0, 0.0), 0.8, be, dCol);
    ci (p, vec2( -0.0, -0.15), 0.66, bl, dCol);
    ci (p, vec2( -0.0, -0.15), 0.65, wh, dCol);
    ell(p, vec2(0.19, 0.43), vec2(0.65, 0.7), 0.31, bl, dCol);
    ell(p, vec2(-0.19, 0.43), vec2(0.65, 0.7), 0.31, bl, dCol);
    ell(p, vec2(0.19, 0.43), vec2(0.65, 0.7), 0.3, wh, dCol);
    ell(p, vec2(-0.19, 0.43), vec2(0.65, 0.7), 0.3, wh, dCol);
    ell(p, vec2(0.18, 0.42), vec2(0.4, 0.7), 0.15, bl, dCol);
    ell(p, vec2(-0.18, 0.42), vec2(0.4, 0.7), 0.15, bl, dCol);
    ell(p, vec2(0.2, 0.45), vec2(0.4, 0.7), 0.05, wh, dCol);
    ell(p, vec2(-0.16, 0.45), vec2(0.4, 0.7), 0.05, wh, dCol);
    ci (p, vec2( 0.0, 0.2), 0.12, bl, dCol);
    ci (p, vec2( 0.0, 0.2), 0.11, re, dCol);
    rect (p, vec2( 0.04, 0.23), 0.02, wh, dCol);
    li (p, vec2( 0.0, -0.12), vec2(0.01, 1.0), 0.2, bl, dCol);
    ell(p, vec2(-0.0, -0.45), vec2(0.8, 0.4), 0.51, bl, dCol);
    ell(p, vec2(-0.0, -0.45), vec2(0.8, 0.4), 0.5, or, dCol);
    ell(p, vec2(-0.0, -0.55), vec2(0.9, 0.3), 0.35, bl, dCol);
    ell(p, vec2(-0.0, -0.55), vec2(0.9, 0.3), 0.34, re, dCol);
    li(p, vec2( 0.5, 0.0), vec2(0.9, 0.03), 0.2, bl, dCol);
    li(p, vec2(-0.5, 0.0), vec2(0.9, 0.03), 0.2, bl, dCol);
    sl(true,p, vec2( 0.34, -0.05), vec2(0.9, 0.03), 0.14, bl, dCol);
    sl(true,p, vec2(-0.34, 0.05), vec2(0.9, 0.03), 0.14, bl, dCol);
    sl(false,p, vec2( 0.34, -0.05), vec2(0.9, 0.03), 0.14, bl, dCol);
    sl(false,p, vec2(-0.34, 0.05), vec2(0.9, 0.03), 0.14, bl, dCol);
    gl_FragColor=vec4(dCol, 1.0);
    
}

|||

---


#### 000

@@@
{
    "title": "Slime",
    "author": "masa",
    "description": "Slime with color"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

void main( void ) {
    vec2 p = (gl_FragCoord.xy*2.0-resolution) / min(resolution.x, resolution.y);

    float a = mix(p.x * p.x,  p.y, sin(time));
    float l = 0.3 / length(p + a);

    gl_FragColor = vec4( vec3( sin(time), cos(time), sin(time) ) * l, 1.0 );
}
|||

---


#### 000

@@@
{
    "title": "テレビの砂嵐",
    "author": "y_kogawa",
    "description": "たまに線が入って乱れるのがそれっぽいような気がします"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)

float rand(vec2 co){
    return fract(sin(dot(co.xy ,vec2(12.9898,78.233))) * 43758.5453);
}

void main(void){
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / min(resolution.x, resolution.y);
    vec3 color = vec3(0.0, 0.0, 0.0);
    color += 1.0 - length(rand(p * sin(time * 0.8) * 0.2));
    gl_FragColor = vec4(color, 1.0);
}

|||

---


#### 000

@@@
{
    "title": "4分割",
    "author": "diwao",
    "description": "4分割してそれぞれ時間差で色変更"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

void main() {
    vec2 p = (gl_FragCoord.xy *2.0 - resolution) / resolution.y;
    if (p.x > 0.0) {
        gl_FragColor = vec4(1.0, sin(time * 3.0), 0.5, 1.0);
    } else {
        gl_FragColor = vec4(sin(time * 0.5), 0.5, 0, 1.0);
    }
    
    if (p.y > 0.0) {
        gl_FragColor = vec4(0.5, 0, sin(time * 1.2), 1);
    }
    
    if (p.y > 0.0 && p.x > 0.0) {
        gl_FragColor = vec4(sin(time * 2.0), sin(time * 3.0), sin(time * 0.5), 1.0);
    }
}
|||

---


#### 000

@@@
{
    "title": "ポテチとめだまやき",
    "author": "gyabo",
    "description": "じゃがいも不足らしいので、ポテチと目玉焼きをだしました"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

vec2 rand(vec2 pos)
{
  return
    fract(
      (
        pow(
          pos+2.0,
          pos.yx+2.0
        )*22222.0
      )
    );
}
 
vec2 rand2(vec2 pos)
{
  return rand(rand(pos));
}

vec4 get_color(vec2 p) {
    const float m = 9.0;
    return vec4(abs(sin(rand2(p).x * 0.2 + p.x * m + time) + cos(p.y * m * cos(2.5))));
}

vec2 rot(vec2 p, float a) {
    return vec2(
        p.x * cos(a) - p.y * sin(a),
        p.x * sin(a) + p.y * cos(a)
    );
}

void main() {
    vec2 uv = (gl_FragCoord.xy * 2.0 - resolution) / resolution.y;
    uv = rot(uv, mod(time * 0.02, 1.0));
    gl_FragColor      = get_color(uv);
    gl_FragColor.xyz *= mix(vec3(1,2,3), vec3(3,2,1), gl_FragColor.x) * 0.4;
    if(length(gl_FragColor.xyz) < 0.97) {
        gl_FragColor = get_color(uv * 2.0 + time).yzxw;
        gl_FragColor.xyz *= vec3(0,2,5);
    }
    float j = 1.0 - dot(uv, uv);
    if(mod(time, 6.0) > 3.0) { 
        gl_FragColor.xyz /= (j) * vec3(1,0,0);
    } else {
        gl_FragColor.xyz += (j) * vec3(1,0,0);
    }
    gl_FragColor.xyz *= max(0.0, 1.0 - dot(uv * 0.75, uv));
    gl_FragColor.a  = 1.0;// - fract(time * 3.0);
}

|||

---


#### 000

@@@
{
    "title": "工場出荷時ドラえも○",
    "author": "koi_zoom1",
    "description": "工場出荷時の◯ラえもんです"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

#define wh vec3(1.0)
#define bl vec3(0.0)
#define re vec3(1.0, 0.0, 0.0)
#define or vec3(0.8, 0.2, 0.0)
#define be vec3(1.0, 1.0, 0.1)

void ci(vec2 p, vec2 of, float si, vec3 cl, inout vec3 i){
    float l=length(p - of);
    if(l < si){i=cl;}
    
}

void rect(vec2 p, vec2 of, float si, vec3 cl, inout vec3 i){
    vec2 q=(p - of) / si;
    if(abs(q.x) < 1.0 && abs(q.y) < 1.0){
        i=cl;
        
    }
    
}

void ell(vec2 p, vec2 of, vec2 prop, float si, vec3 cl, inout vec3 i){
    vec2 q=(p - of) / prop;
    if(length(q) < si){
        i=cl;
        
    }
}

void li(vec2 p, vec2 of, vec2 v,float si, vec3 cl, inout vec3 i){
    vec2 q=(p - of) / si;
    if(abs(q.x) < v.x && abs(q.y)< v.y){
        i=cl;
    }
}

void sl(bool flg, vec2 p, vec2 of, vec2 v,float si, vec3 cl, inout vec3 i){
    float s=sin(0.15);
    float c=cos(sin(2.0));
    vec2 q;
    if(flg==true){
        q=((p * mat2(c, -s, s, c)) - of) / si;
    }else{
        q=((p * mat2(-c, -s, -s, c)) - of) / si;
        
    }
    if(abs(q.x) < v.x && abs(q.y)< v.y){
        i=cl;
        
    }
    
}

vec2 rot(vec2 p,float a){
    float c = cos(a);
    float s = sin(a);
    return vec2(
        (c * p.x - s * p.y) / sin(time),
        (s * p.x + c * p.y) / sin(time)
        );
}

void main(void){
    vec3 dCol=wh;
    vec2 p=(gl_FragCoord.xy * 2.0 - resolution) / 
    min(resolution.x, resolution.y);
    p = rot(p,time*1.0);
    p.x +=cos(time*2.0)*0.225;
    p.y +=sin(time*2.0)*0.225;
    ci (p, vec2( 0.0, 0.0), 0.81, bl, dCol);
    ci (p, vec2( 0.0, 0.0), 0.8, be, dCol);
    ci (p, vec2( -0.0, -0.15), 0.66, bl, dCol);
    ci (p, vec2( -0.0, -0.15), 0.65, wh, dCol);
    ell(p, vec2(0.19, 0.43), vec2(0.65, 0.7), 0.31, bl, dCol);
    ell(p, vec2(-0.19, 0.43), vec2(0.65, 0.7), 0.31, bl, dCol);
    ell(p, vec2(0.19, 0.43), vec2(0.65, 0.7), 0.3, wh, dCol);
    ell(p, vec2(-0.19, 0.43), vec2(0.65, 0.7), 0.3, wh, dCol);
    ell(p, vec2(0.18, 0.42), vec2(0.4, 0.7), 0.15, bl, dCol);
    ell(p, vec2(-0.18, 0.42), vec2(0.4, 0.7), 0.15, bl, dCol);
    ell(p, vec2(0.2, 0.45), vec2(0.4, 0.7), 0.05, wh, dCol);
    ell(p, vec2(-0.16, 0.45), vec2(0.4, 0.7), 0.05, wh, dCol);
    ci (p, vec2( 0.0, 0.2), 0.12, bl, dCol);
    ci (p, vec2( 0.0, 0.2), 0.11, re, dCol);
    rect (p, vec2( 0.04, 0.23), 0.02, wh, dCol);
    li (p, vec2( 0.0, -0.12), vec2(0.01, 1.0), 0.2, bl, dCol);
    ell(p, vec2(-0.0, -0.45), vec2(0.8, 0.4), 0.51, bl, dCol);
    ell(p, vec2(-0.0, -0.45), vec2(0.8, 0.4), 0.5, or, dCol);
    ell(p, vec2(-0.0, -0.55), vec2(0.9, 0.3), 0.35, bl, dCol);
    ell(p, vec2(-0.0, -0.55), vec2(0.9, 0.3), 0.34, re, dCol);
    li(p, vec2( 0.5, 0.0), vec2(0.9, 0.03), 0.2, bl, dCol);
    li(p, vec2(-0.5, 0.0), vec2(0.9, 0.03), 0.2, bl, dCol);
    sl(true,p, vec2( 0.34, -0.05), vec2(0.9, 0.03), 0.14, bl, dCol);
    sl(true,p, vec2(-0.34, 0.05), vec2(0.9, 0.03), 0.14, bl, dCol);
    sl(false,p, vec2( 0.34, -0.05), vec2(0.9, 0.03), 0.14, bl, dCol);
    sl(false,p, vec2(-0.34, 0.05), vec2(0.9, 0.03), 0.14, bl, dCol);
    gl_FragColor=vec4(dCol, 1.0);
    
}

|||

---


#### 000

@@@
{
    "title": "impluse",
    "author": "ushio",
    "description": "impluseimpluseimpluse"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

vec3 hsv(float h, float s, float v){
    vec4 t = vec4(1.0, 2.0 / 3.0, 1.0 / 3.0, 3.0);
    vec3 p = abs(fract(vec3(h) + t.xyz) * 6.0 - vec3(t.w));
    return v * mix(vec3(t.x), clamp(p - vec3(t.x), 0.0, 1.0), s);
}

vec3 screen(vec3 a, vec3 b) {
    return vec3(1.0) - (vec3(1.0) - a) * (vec3(1.0) - b);
}
float impulse(float x, float a) {
    return (1.0 / a) * x * exp(1.0 - 1.0 / a * x);
}
void main() {
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / min(resolution.x, resolution.y);
    
    vec3 color = vec3(0.0);
    
    for(int i = 0 ; i < 20 ; ++i) {
    	float im = impulse(mod(time + float(i) * 0.01, 0.4), 0.05);
    	
    	vec2 c = vec2(cos(time + float(i) * 0.2), sin(time + float(i) * sin(time)));
        vec3 color_hsv = hsv(float(i) / 20.0 * mix(1.0, 3.0, im), 1.0, 1.0);

    	float v = 1.0 - smoothstep(0.01, mix(0.05, 0.1, im), fract(-0.1 + pow(distance(p, c) + 0.1, 2.0) * mix(1.0, 0.4, im)));
    	color = screen(color, vec3(v) * color_hsv);
    }
    
    // for(int i = 0 ; i < 50 ; ++i) {
    // 	vec2 c = vec2(cos(time + float(i) * 0.2), sin(time + float(i) * 0.3));
    // 	float v = 1.0 - smoothstep(0.03, 0.1, distance(p, c));
    // 	color = screen(color, vec3(v));
    // }
    
    gl_FragColor.rgb = color;
    
    gl_FragColor.a = 1.0;
    
    vec4 backcolor = texture2D(backbuffer, gl_FragCoord.xy / min(resolution.x, resolution.y));
    gl_FragColor = mix(backcolor, gl_FragColor, 0.5);
}

|||

---


#### 000

@@@
{
    "title": "男と女",
    "author": "xxx",
    "description": "同じところをいったりきたりしているがすれ違う恋"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

void main(){
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / min(resolution.x, resolution.y);
    float r = 0.1 / length(p + time) + sin(time);
    float g = 0.2 / length(p - sin(time));
    float b = 0.3 / length(p + cos(time));
    gl_FragColor = vec4(vec3(r, g, b), 1.0);
}

|||

---


#### 000

@@@
{
    "title": "中心がやばいやつ",
    "author": "diwao",
    "description": "偶然の産物"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

void main() {
    vec2 p = (gl_FragCoord.xy *2.0 - resolution) / resolution.y;
    float f = sin(time * 0.5) * 50.0 / length(p);
    gl_FragColor = vec4(vec3(sin(f)), 1.0);
}
|||

---


#### 000

@@@
{
    "title": "ごちゃまぜ",
    "author": "ao",
    "description": "綺麗に見える程度にいろいろ混ぜました"
}
@@@

---

|||
precision mediump float;
uniform vec2 resolution;
uniform float time;

#define MAX_TIME 60
 
float rings(vec2 p)
{
  return sin(length(p)*16.0);
}

vec4 get_color(vec2 p)
{
    return vec4(sin(length(p) * 70.0));
}

float map(vec3 p)
{
    float temp = length(mod(p,2.0) - 1.0) - 0.1;
    float temp_2 = temp * 3.14; 
    return sin(temp * time);
}

vec3 rot(vec3 ip)
{
    float ax = 2.0;
    float a = sin(time * ax);
    float b = cos(time * ax);
    float x = a -b;
    float y = b + a;
    ip.x *= x;
    ip.y *= y;
    ip.z *= x*y;
    return ip;
}

float _s(vec2 sp)
{
    vec2 p = sp*10.0 - vec2(10.0);
    vec2 i = p;
    float c = 1.0;
    
    float inten = 0.01;

    
    float t = time* (1.0 - (1.2 / float(0+1)));
    i = p + vec2(cos(t - i.x) + sin(t + i.y), sin(t - i.y) + cos(t + i.x));
    c += 1.0/length(vec2(p.x / (sin(i.x+t)/inten),p.y / (cos(i.y+t)/inten)));
    c /= 1.0;
    c = 1.5-sqrt(c);
    c += 2.0;
    return c;
}
 
void main() 
{
  vec2 uv = (gl_FragCoord.xy*2.0 -resolution) / resolution.y;
 
  vec3 pos = vec3(0.0,0.0,-1.0); // xyz
  vec3 dir = normalize(vec3(uv,time));
  float t = 0.0;
  for(int i=0;i<100;i++)
  {
  	vec3 temp = pos + dir *t;
  	t += map(temp);
  }
  vec3 ip = pos + dir *t;
  ip = rot(ip);
  ip += _s(uv);
  gl_FragColor.xyz = vec3(ip * 0.333);
  
  gl_FragColor.a = 1.0;
}
|||

---


#### 000

@@@
{
    "title": "波乗り三兄弟",
    "author": "doxas",
    "description": "あやしげな動き……"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

vec3 hsv(float h, float s, float v){
    vec4 t = vec4(1.0, 2.0 / 3.0, 1.0 / 3.0, 3.0);
    vec3 p = abs(fract(vec3(h) + t.xyz) * 6.0 - vec3(t.w));
    return v * mix(vec3(t.x), clamp(p - vec3(t.x), 0.0, 1.0), s);
}

void main(){
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / min(resolution.x, resolution.y);
    float h = step(10.0, mod((p.x - time * 0.2) * 500.0, 20.0));
    float g = sin(p.x * 10.0 + time) * 0.075;
    float f = step(p.y + g, 0.0);
    float c = cos(time * 1.5) * 2.0 + 1.0;
    float d = cos(time * 1.7) * 2.0 + 1.0;
    float e = cos(time * 2.0) * 2.0 + 1.0;
    vec2 q = p + vec2(c, g);
    vec2 r = p + vec2(d, g);
    vec2 s = p + vec2(e, g);
    float i = pow(0.12 / length(q), 20.0);
    float j = pow(0.15 / length(r), 20.0);
    float k = pow(0.20 / length(s), 20.0);
    float sun = 1.0;
    if(f >= 0.0){
    	sun = 1.5 / length(p);
    }
    gl_FragColor = vec4(vec3(f * h * sun) * vec3(0.0, 0.5, 1.0) + vec3(i, j, k), 1.0);
}


|||

---


#### 000

@@@
{
    "title": "ドラえ○んに見える瞬間",
    "author": "koi_zoom1",
    "description": "パチモノから本物への間を行ったり来たりします。目の位置が肝！"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

#define wh vec3(1.0)
#define bl vec3(0.0)
#define re vec3(1.0, 0.0, 0.0)
#define or vec3(0.8, 0.2, 0.0)
#define be vec3(1.0, 1.0, 0.1)

void ci(vec2 p, vec2 of, float si, vec3 cl, inout vec3 i){
    float l=length(p - of);
    if(l < si){i=cl;}
    
}

void rect(vec2 p, vec2 of, float si, vec3 cl, inout vec3 i){
    vec2 q=(p - of) / si;
    if(abs(q.x) < 1.0 && abs(q.y) < 1.0){
        i=cl;
        
    }
    
}

void ell(vec2 p, vec2 of, vec2 prop, float si, vec3 cl, inout vec3 i){
    vec2 q=(p - of) / prop;
    if(length(q) < si){
        i=cl;
        
    }
}

void li(vec2 p, vec2 of, vec2 v,float si, vec3 cl, inout vec3 i){
    vec2 q=(p - of) / si;
    if(abs(q.x) < v.x && abs(q.y)< v.y){
        i=cl;
    }
}

void sl(bool flg, vec2 p, vec2 of, vec2 v,float si, vec3 cl, inout vec3 i){
    float s=sin(0.15);
    float c=cos(sin(2.0));
    vec2 q;
    if(flg==true){
        q=((p * mat2(c, -s, s, c)) - of) / si;
    }else{
        q=((p * mat2(-c, -s, -s, c)) - of) / si;
        
    }
    if(abs(q.x) < v.x && abs(q.y)< v.y){
        i=cl;
        
    }
    
}

vec2 rot(vec2 p,float a){
    float c = cos(a);
    float s = sin(a);
    return vec2(
        (c * p.x - s * p.y) / sin(time*2.0),
        (s * p.x + c * p.y) / sin(time*-2.0)
        );
}

void main(void){
    vec3 dCol=wh;
    vec2 p=(gl_FragCoord.xy * 2.0 - resolution) / 
    min(resolution.x, resolution.y);
    //p = rot(p,time*3.0);
    //p.x +=cos(time*2.0)*0.225;
    //p.y +=sin(time*2.0)*0.225;
    ci (p, vec2( 0.0, 0.0), 0.81, bl, dCol);
    ci (p, vec2( 0.0, 0.0), 0.8, be, dCol);
    ci (p, vec2( -0.0, -0.15+sin(time)*0.13), 0.66+sin(time)*0.13, bl, dCol);
    ci (p, vec2( -0.0, -0.15+sin(time)*0.13), 0.65+sin(time)*0.13, wh, dCol);
    ell(p, vec2(0.19, 0.43), vec2(0.65, 0.7), 0.31, bl, dCol);
    ell(p, vec2(-0.19, 0.43), vec2(0.65, 0.7), 0.31, bl, dCol);
    ell(p, vec2(0.19, 0.43), vec2(0.65, 0.7), 0.3, wh, dCol);
    ell(p, vec2(-0.19, 0.43), vec2(0.65, 0.7), 0.3, wh, dCol);
    ell(p, vec2(0.18, 0.42), vec2(0.4, 0.7), 0.15, bl, dCol);
    ell(p, vec2(-0.18, 0.42), vec2(0.4, 0.7), 0.15, bl, dCol);
    ell(p, vec2(0.2, 0.45), vec2(0.4, 0.7), 0.05, wh, dCol);
    ell(p, vec2(-0.16, 0.45), vec2(0.4, 0.7), 0.05, wh, dCol);
    ci (p, vec2( 0.0, 0.2), 0.12, bl, dCol);
    ci (p, vec2( 0.0, 0.2), 0.11, re, dCol);
    rect (p, vec2( 0.04, 0.23), 0.02, wh, dCol);
    li (p, vec2( 0.0, -0.12), vec2(0.01, 1.0), 0.2, bl, dCol);
    ell(p, vec2(-0.0, -0.45), vec2(0.8, 0.4), 0.51, bl, dCol);
    ell(p, vec2(-0.0, -0.45), vec2(0.8, 0.4), 0.5, or, dCol);
    ell(p, vec2(-0.0, -0.55), vec2(0.9, 0.3), 0.35, bl, dCol);
    ell(p, vec2(-0.0, -0.55), vec2(0.9, 0.3), 0.34, re, dCol);
    li(p, vec2( 0.5, 0.0), vec2(0.9, 0.03), 0.2, bl, dCol);
    li(p, vec2(-0.5, 0.0), vec2(0.9, 0.03), 0.2, bl, dCol);
    sl(true,p, vec2( 0.34, -0.05), vec2(0.9, 0.03), 0.14, bl, dCol);
    sl(true,p, vec2(-0.34, 0.05), vec2(0.9, 0.03), 0.14, bl, dCol);
    sl(false,p, vec2( 0.34, -0.05), vec2(0.9, 0.03), 0.14, bl, dCol);
    sl(false,p, vec2(-0.34, 0.05), vec2(0.9, 0.03), 0.14, bl, dCol);
    gl_FragColor=vec4(dCol, 1.0);
    
}

|||

---


#### 000

@@@
{
    "title": "謎の魔法陣",
    "author": "ShoutaWATANABE",
    "description": "tan関数がうまく作用して魔法陣のようになりました。"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

float rings(vec2 p)
{
  return sin(length(p)*16.0);
}

float rings2(vec2 p)
{
  return cos(length(p)*16.0);
}

float rings3(vec2 p)
{
  return tan(length(p)*16.0);
}

void main() {
  vec2 pos = (gl_FragCoord.xy*2.0 -resolution) / (resolution.x, resolution.y);
 
  gl_FragColor = vec4(sin(rings(pos)*sin(time)),cos(rings3(pos))*cos(time), rings(pos), 1.0);
}

|||

---


#### 000

@@@
{
    "title": "色々",
    "author": "tanshio",
    "description": "向かってくる色"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

float sdCone( vec3 p, vec2 c ){
    // c must be normalized
    float q = length(p.xy);
    return dot(c,vec2(q,p.z));
}

float plasma(vec2 p)
{
  p*=10.0;
  return (sin(p.x*sin(time))*0.25+0.25)+(sin(p.y*cos(time))*0.25+0.25);
}

float rand(vec2 co){
    return fract(sin(dot(co.xy ,vec2(12.9898,78.233))) * 43758.5453);
}
 
void main() {
  vec2 pos = (gl_FragCoord.xy*2.0 -resolution) / resolution.y;
  gl_FragColor = vec4(sdCone(vec3(0.0,10.0,10.0),normalize(vec2(1.0,1.0))));
  gl_FragColor.xyz *= vec3(abs(cos(time))/0.2,abs(sin(time))/0.2,tan(time));
  gl_FragColor *= vec4(plasma(pos));
  gl_FragColor.xyz *= vec3(rand(pos),rand(pos),rand(pos));
  gl_FragColor.a = 0.5;
}
|||

---


#### 000

@@@
{
    "title": "sand art",
    "author": "ushio",
    "description": "sand art"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

vec3 hsv(float h, float s, float v){
    vec4 t = vec4(1.0, 2.0 / 3.0, 1.0 / 3.0, 3.0);
    vec3 p = abs(fract(vec3(h) + t.xyz) * 6.0 - vec3(t.w));
    return v * mix(vec3(t.x), clamp(p - vec3(t.x), 0.0, 1.0), s);
}

vec3 screen(vec3 a, vec3 b) {
    return vec3(1.0) - (vec3(1.0) - a) * (vec3(1.0) - b);
}
float impulse(float x, float a) {
    return (1.0 / a) * x * exp(1.0 - 1.0 / a * x);
}
void main() {
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / min(resolution.x, resolution.y);
    
    // p.y += 0.2 * sin(p.x * 3.0 + time) * sin(time * 0.3);
   //  p.x += 0.2 * sin(p.y * 10.0 + time) * sin(time * 0.3);
    
    vec3 color = vec3(0.0);
    
    for(int i = 0 ; i < 50 ; ++i) {
    	float im = impulse(mod(time + float(i) * 0.01, 0.4), 0.05);
    	
    	vec3 hsvcolor = hsv(color.r, im, 1.0);
    	
    	vec2 c = vec2(cos(time + float(i) * 0.2), sin(time + float(i) * sin(time)));
        // vec3 color_hsv = hsv(float(i) / 20.0 * mix(1.0, 3.0, im), 1.0, 1.0);

    	float v = 1.0 - smoothstep(0.3, 4.0, fract(-0.1 + pow(distance(p, c) + 0.1, 1.0)));
    	// color = screen(color, vec3(v));
    	color += vec3(v) * hsvcolor;
    }
    color = fract(color * mix(0.1, 1.0, sin(time) * 0.5 + 0.5));
    
    // color = hsv(color.r, 1.0, 1.0);
    
    // for(int i = 0 ; i < 50 ; ++i) {
    // 	vec2 c = vec2(cos(time + float(i) * 0.2), sin(time + float(i) * 0.3));
    // 	float v = 1.0 - smoothstep(0.03, 0.1, distance(p, c));
    // 	color = screen(color, vec3(v));
    // }
    
    gl_FragColor.rgb = color;
    
    gl_FragColor.a = 1.0;
    
    vec4 backcolor = texture2D(backbuffer, gl_FragCoord.xy / min(resolution.x, resolution.y));
    gl_FragColor = mix(backcolor, gl_FragColor, 0.5);
}

|||

---


#### 000

@@@
{
    "title": "エネルギー的なものが動いてる",
    "author": "y_kogawa",
    "description": "何だかよくわからないけど綺麗っぽいもの"
}
@@@

---

|||
precision mediump float;
uniform float time;
uniform vec2 mouse;
uniform vec2 resolution;

void main()
{
    float amplitude = sin(time) * .4;
    float glowT = 2.;
    float glowFactor = mix( 0.015, 0.035, glowT );
    
    vec2 p = vec2(0.0, 0.8) + 4.*gl_FragCoord.xy / resolution.xy;
    
    vec3 c = vec3(.0);
    vec3 basecol[4];
    basecol[0] = vec3(1., 1.25, .25);
    basecol[1] = vec3(.25, 1., .25);

    c += basecol[0] * ( glowFactor * abs( 1.0 / tan(p.y + cos( p.x + time ) * amplitude ) )) * (.5-.4*abs(cos(p.x+time*8.)));
    c += basecol[1] * ( glowFactor * abs( 1.0 / tan(p.y + cos( p.x + time+2. ) * amplitude ) )) * (.5-.8*abs(cos(p.x+time*8.)));

    gl_FragColor = vec4( c, 1.0 );

}
|||

---


---

## enjoy shader life

---

## enjoy shader life

### thank you!!

---


