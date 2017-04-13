
---

#### 000

@@@
{
    "title": "arctangent demo",
    "author": "doxas",
    "description": "arctangent distortion."
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;
uniform vec2  mouse;
uniform float time;
uniform sampler2D backbuffer;

const vec3 pinkColor = vec3(1.0, 0.1, 0.5);
const vec3 blueColor = vec3(0.1, 0.3, 0.9);

float waveNeon(vec2 p, float power, float width, float height, float speed){
    float x = cos(abs(p.x * width));
    float y = power / abs(p.y + sin(p.x * 25.0 + time * speed) * height);
    return max(x * y, 0.0);
}

void main(){
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / min(resolution.x, resolution.y);
    vec2 m = mouse * 2.0 - 1.0;
    float t = min(time, 2.0) * 0.5;
    p = p * abs(atan(p.y / p.x));
    float a = waveNeon(p, 0.2, 5.0, 0.25 + abs(m.x), 0.75);
    float b = waveNeon(p, 0.5, 2.5, 0.5  + abs(m.y), 0.25);
    gl_FragColor = vec4((pinkColor * a + blueColor * b) * t, 1.0);
}
|||

---

#### 000

@@@
{
    "title": "HELLOWORLD!!!!",
    "author": "notargs",
    "description": "printf(\"Hello World\");"
}
@@@

---

|||
#ifdef GL_ES
precision mediump float;
#endif

#extension GL_OES_standard_derivatives : enable

uniform float time;
uniform vec2 mouse;
uniform vec2 resolution;

float sphere(vec3 pos, float size)
{
    return length(pos) - size;
}

float udRoundBox( vec3 p, vec3 b, float r )
{
    return length(max(abs(p)-b,0.0)) - r;
}

float text(vec3 pos)
{
    return min(min(min(min(min(min(min(min(min(min(min(min(min(min(min(min(min(min(min(min(min(min(min(min(min(min(min(min(min(min(min(min(min(
        udRoundBox(pos - vec3(-4.59, 0.00, 0.00), vec3(0.13, 0.57, 0.13), 0.05),
        udRoundBox(pos - vec3(-3.60, 0.00, 0.00), vec3(0.13, 0.57, 0.13), 0.05)),
        udRoundBox(pos - vec3(3.51, 0.00, 0.00), vec3(0.13, 0.57, 0.13), 0.05)),
        udRoundBox(pos - vec3(4.48, 0.00, 0.00), vec3(0.13, 0.57, 0.13), 0.05)),
        udRoundBox(pos - vec3(4.77, -0.49, 0.00), vec3(0.32, 0.12, 0.13), 0.05)),
        udRoundBox(pos - vec3(-4.30, -0.49, 0.00), vec3(0.37, 0.12, 0.13), 0.05)),
        udRoundBox(pos - vec3(-2.62, 0.00, 0.00), vec3(0.13, 0.57, 0.13), 0.05)),
        udRoundBox(pos - vec3(2.39, 0.00, 0.00), vec3(0.13, 0.57, 0.13), 0.05)),
        udRoundBox(pos - vec3(5.10, 0.00, 0.00), vec3(0.15, 0.36, 0.13), 0.05)),
        udRoundBox(pos - vec3(-1.61, 0.00, 0.00), vec3(0.13, 0.57, 0.13), 0.05)),
        udRoundBox(pos - vec3(3.00, 0.14, 0.00), vec3(0.13, 0.31, 0.13), 0.05)),
        udRoundBox(pos - vec3(4.77, 0.47, 0.00), vec3(0.32, 0.12, 0.13), 0.05)),
        udRoundBox(pos - vec3(-0.15, 0.00, 0.00), vec3(0.13, 0.57, 0.13), 0.05)),
        udRoundBox(pos - vec3(1.91, 0.00, 0.00), vec3(0.13, 0.57, 0.13), 0.05)),
        udRoundBox(pos - vec3(0.33, -0.49, 0.00), vec3(0.53, 0.12, 0.13), 0.05)),
        udRoundBox(pos - vec3(-0.99, 0.00, 0.00), vec3(0.13, 0.57, 0.13), 0.05)),
        udRoundBox(pos - vec3(2.84, -0.27, 0.00), vec3(0.13, 0.31, 0.13), 0.05)),
        udRoundBox(pos - vec3(-2.32, -0.49, 0.00), vec3(0.37, 0.12, 0.13), 0.05)),
        udRoundBox(pos - vec3(-4.30, 0.00, 0.00), vec3(0.37, 0.12, 0.13), 0.05)),
        udRoundBox(pos - vec3(-1.32, 0.47, 0.00), vec3(0.37, 0.12, 0.13), 0.05)),
        udRoundBox(pos - vec3(1.30, 0.00, 0.00), vec3(0.13, 0.57, 0.13), 0.05)),
        udRoundBox(pos - vec3(-4.30, 0.45, 0.00), vec3(0.37, 0.12, 0.13), 0.05)),
        udRoundBox(pos - vec3(-3.30, -0.49, 0.00), vec3(0.37, 0.12, 0.13), 0.05)),
        udRoundBox(pos - vec3(0.77, 0.00, 0.00), vec3(0.13, 0.57, 0.13), 0.05)),
        udRoundBox(pos - vec3(2.68, -0.13, 0.00), vec3(0.37, 0.12, 0.13), 0.05)),
        udRoundBox(pos - vec3(2.68, 0.47, 0.00), vec3(0.37, 0.12, 0.13), 0.05)),
        udRoundBox(pos - vec3(0.30, 0.00, 0.00), vec3(0.13, 0.57, 0.13), 0.05)),
        udRoundBox(pos - vec3(1.59, 0.47, 0.00), vec3(0.37, 0.12, 0.13), 0.05)),
        udRoundBox(pos - vec3(1.59, -0.49, 0.00), vec3(0.37, 0.12, 0.13), 0.05)),
        udRoundBox(pos - vec3(-1.32, -0.49, 0.00), vec3(0.37, 0.12, 0.13), 0.05)),
        udRoundBox(pos - vec3(3.80, -0.49, 0.00), vec3(0.37, 0.12, 0.13), 0.05)),
        udRoundBox(pos - vec3(-5.38, 0.00, 0.00), vec3(0.36, 0.16, 0.13), 0.05)),
        udRoundBox(pos - vec3(-5.69, 0.00, 0.00), vec3(0.13, 0.57, 0.13), 0.05)),
        udRoundBox(pos - vec3(-5.09, 0.00, 0.00), vec3(0.13, 0.57, 0.13), 0.05));
}




float sdPlane( vec3 p, vec4 n )
{
    return dot(p,n.xyz) + n.w;
}

float planes(vec3 p)
{
    return min(
        sdPlane(p, vec4(0, 1, 0, 2)),
        sdPlane(p, vec4(0, -1, 0, 2)));
}

float dist(vec3 p) 
{
    return min(
        text(p),
        planes(p));
}

vec3 getColor(vec3 p)
{
    if (planes(p) < 0.1)
    {
        return vec3(0.9, 0.9, 1);
    }
    return vec3(0.9, 0.2, 0.9);
}

vec3 getNormal(vec3 p)
{
    float ep = 0.001;
    return normalize(vec3(
        dist(p + vec3(ep, 0, 0)) - dist(p - vec3(ep, 0, 0)),
        dist(p + vec3(0, ep, 0)) - dist(p - vec3(0, ep, 0)),
        dist(p + vec3(0, 0, ep)) - dist(p - vec3(0, 0, ep))
    ));
}

mat3 rotY(float a)
{
    return mat3(cos(a), 0, -sin(a),
           0, 1, 0,
           sin(a), 0, cos(a));
}

void main(void) 
{
    vec2 tex = (gl_FragCoord.xy - resolution.xy / 2.0) / resolution.y;
    
    vec3 color = vec3(1, 1, 1);
    
    mat3 rot = rotY(sin(time * 4.0));
    
    vec3 pos = rot * vec3(0, 0, -10);
    vec3 dir = rot * normalize(vec3(tex, 1.0));
    
    for (int i = 0; i < 32; ++i)
    {
        float d = dist(pos);
        if (d < 0.1) 
        {
            vec3 normal = getNormal(pos);
            
            float light = max(0.0, dot(vec3(1, 1, 1), normal));
            
            light += 0.5;
            color *= getColor(pos);
            dir = reflect(dir, normal);
            pos += dir * 0.1;
        }
        
        pos += dir * d;
    }
    
    gl_FragColor = vec4(color, 1.0);

}
|||

---


#### 000

@@@
{
    "title": "ぐねぐね",
    "author": "prototechno",
    "description": "マウスでドッグして ぐねぐねする何か。。。"
}
@@@

---

|||

#ifdef GL_ES
precision mediump float;
#endif
 
uniform float time;
uniform vec2 mouse;
uniform vec2 resolution;
 
void main(void){
    vec2 v = (gl_FragCoord.xy - resolution/2.0) / min(resolution.y,resolution.x) * 20.0;
    vec2 vv = v; vec2 vvv = v;
    float tm = time*0.003;
    vec2 mspt = (vec2(
            sin(tm)+cos(tm*0.2)+sin(tm*0.5)+cos(tm*-0.4)+sin(tm*1.3),
            cos(tm)+sin(tm*0.1)+cos(tm*0.8)+sin(tm*-1.1)+cos(tm*1.5)
            )+1.0)*0.1; //5x harmonics, scale back to [0,1]
    float R = 0.0;
    float RR = 0.0;
    float RRR = 0.0;
    float a = (.6-mspt.x)*6.2;
//	float C = cos(a);
    float C = tan(a);
    float S = sin(a);
    vec2 xa=vec2(C, -S);
    vec2 ya=vec2(S, C);
    vec2 shift = vec2( 0, 1.62);
    float Z = 1.0 + mspt.y*6.0;
    float ZZ = 1.0 + (mspt.y)*6.2;
    float ZZZ = 1.0 + (mspt.y)*6.9;

    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / min(resolution.x, resolution.y);
    float f = 0.1 / length(p - (mouse * 2.0 - 1.0));

    for ( int i = 0; i < 40; i++ ){
        float r = dot(v,v);
        if ( r > 1.0 )
        {
            r = (1.0)/r ;
            v.x = v.x * r;
            v.y = v.y * r;
        }
        R *= .99;
        R += r;
        if(i < 39){
            RR *= .99;
            RR += r;
            if(i < 38){
                RRR *= .99;
                RRR += r;
            }
        }
        
        v = vec2( dot(v +f, xa +f), dot(v, ya)) * Z + shift;
    }

    float c = ((mod(R,2.0)>1.0)?1.0+fract(R):fract(R) + f/3.0);
    float cc = ((mod(RR,2.0)>1.0)?1.0-fract(RR):fract(RR) + f/0.3);
    float ccc = ((mod(RRR,2.0)>1.0)?1.0-fract(RRR):fract(RRR) + f/5.0);
    gl_FragColor = vec4(ccc, cc, c, 1.0); 
}

|||

---


#### 000

@@@
{
    "title": "Sushi",
    "author": "notargs",
    "description": "transformSushiSpace関数が増えました"
}
@@@

---

|||
#ifdef GL_ES
precision mediump float;
#endif

#extension GL_OES_standard_derivatives : enable

uniform float time;
uniform vec2 mouse;
uniform vec2 resolution;

mat3 rotY(float a)
{
    return mat3(cos(a), 0, -sin(a),
           0, 1, 0,
           sin(a), 0, cos(a));
}
// 球を定義
float sphere(vec3 p)
{
    return length(p) - 1.0;
}

float udRoundBox( vec3 p, vec3 b, float r )
{
    return length(max(abs(p)-b,0.0)) - r;
}

vec3 transformSushiSpace(vec3 p)
{
    mat3 rot = rotY(time);
    
    p = mod(p, 10.0) - 5.0;
    p = rot * p;
    return p;
}

float salmon(vec3 p)
{
    p = transformSushiSpace(p);
    return udRoundBox(p + vec3(0, -0.35 - cos(p.x / 3.0), 0), vec3(3.0, 0.04, 1.0), 0.2);
}


float shari(vec3 p)
{
    p = transformSushiSpace(p);
    return udRoundBox(p, vec3(1.5, 0.3, 0.3), 1.0);
}


vec3 getColor(vec3 p)
{
    if (salmon(p) < 0.1)
    {	
        p = transformSushiSpace(p);
        return mix(vec3(1, 0.3, 0), vec3(1, 1, 1), clamp(sin(p.x * 5.0 + abs(p.z)) - 0.5, 0.0, 1.0));
    }
    
    return vec3(1, 1, 1);
}


// 距離感数
float dist(vec3 p)
{
    return min(salmon(p), shari(p));
}

vec3 getNormal(vec3 p)
{
    float ep = 0.001;
    return normalize(vec3(dist(p) - dist(p - vec3(ep, 0, 0)),
                 dist(p) - dist(p - vec3(0, ep, 0)),
                 dist(p) - dist(p - vec3(0, 0, ep))));
}

void main( void ) {

    vec2 tex = (gl_FragCoord.xy - resolution.xy / 2.0) / resolution.y;
    
    mat3 rot = rotY(time * 0.1);
    
    vec3 pos = rot * vec3(0, 0, -10);
    vec3 dir = rot * normalize(vec3(tex, 0.8));
    
    vec3 color = vec3(0.0, 0.0, 0.0);
    
    // レイマーチング
    for(float i = 0.0; i < 32.0; i++)
    {
        float d = dist(pos);
        if (d < 0.1)
        {
            color = (max(dot(vec3(1, 1, -1), getNormal(pos)), 0.0) + 0.2) * getColor(pos);
            break;
        }
        
        pos += dir * d;
    }
    
    gl_FragColor = vec4(color, 1.0 );

}
|||

---


#### 000

@@@
{
    "title": "目が痛いエフェクト",
    "author": "watanabe",
    "description": " sin をずらしてカラフルにしました。"
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
    //-1 〜 1
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / min(resolution.x, resolution.y);
    
    float e = 0.5 / length(p);
    
    float r1 = sin(time) * 120.0;
    float r2 = sin(time*0.9) * 90.0;
    float r3 = sin(time*0.7) * 40.0;
    
    float rr=sin(length(p*r1)-time*10.0) * e;
    float gg=sin(length(p*r2)-time*10.0) * e;
    float bb=sin(length(p*r3)-time*10.0) * e;
    
    gl_FragColor = vec4(vec3(rr,gg,bb), 1.0);
    
}

|||

---


#### 000

@@@
{
    "title": "test",
    "author": "ndm",
    "description": "test"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
//uniform sampler2D backbuffer; // previous scene texture

vec3 hsv(float h, float s, float v){
    vec4 t = vec4(1.0, 2.0 / 3.0, 1.0 / 3.0, 3.0);
    vec3 p = abs(fract(vec3(h) + t.xyz) * 6.0 - vec3(t.w));
    return v * mix(vec3(t.x), clamp(p - vec3(t.x), 0.0, 1.0), s);
}

void main(){
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / resolution;
    vec2 m = mouse * 10.0;
    float e = 0.1 / length(p);
    float fr = sin(length((p * 10.0) / m) + time * 2.0);
    float fg = sin(length((p * 10.0) / m) + time * 4.0);
    float fb = sin(length((p * 10.0) / m) + time * 16.0);

    gl_FragColor = vec4((e * vec3(fr, fg, fb)), 1.0);
}
|||

---


#### 000

@@@
{
    "title": "アンモナイト",
    "author": "sawa-zen",
    "description": "アンモナイトのような模様が流れる作品です。マウス操作で若干模様が変わるのでそちらもお楽しみください。"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

const float PI = 3.1415926;
const float PI2 = PI * 2.0;

vec3 hsv(float h, float s, float v){
    vec4 t = vec4(1.0, 2.0 / 3.0, 1.0 / 3.0, 3.0);
    vec3 p = abs(fract(vec3(h) + t.xyz) * 6.0 - vec3(t.w));
    return v * mix(vec3(t.x), clamp(p - vec3(t.x), 0.0, 1.0), s);
}

void main(){
    // (-512 ~ 512) / 512 == -1 ~ 1
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / resolution;
    // length = ベクトルの長さ
    vec2 m = mouse * 2.0 - 1.0; // -1 ~ 1;
    float e = 0.1 / length(p / m);
    float f = tan(length(p * 5.0) - time * 10.0);
    float a = (atan(p.y, p.x) + PI) / PI2;
    float f2 = sin(length(p * 50.0 * a));
    
    vec3 color = hsv(time / 10.0, 0.5, 1.0);
    
    gl_FragColor = vec4(tan(vec3(e / f / f2 + color)), 1.0);
}
|||

---


#### 000

@@@
{
    "title": "スポットライト",
    "author": "nyamogera",
    "description": "光がふわふわ回転します。"
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
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / resolution ;
    
    float sr = sin(time*3.0)*0.5;
    float cr = cos(time*3.0)*0.5;
    
    float sg = sin(time*4.0)*0.5;
    float cg = cos(time*4.0)*0.5;
    
    float sb = sin(time*2.0)*0.5;
    float cb = cos(time*2.0)*0.5;
    
    
    float r = (abs(sin(time)) + 0.1) / length( p + vec2(cr,sr)) ;
    float g = (abs(sin(time)) + 0.1) / length( p + vec2(cg,sg)) ;
    float b = (abs(sin(time)) + 0.1) / length( p + vec2(cb,sb)) ;
    
    gl_FragColor = vec4(vec3(r,g,b), 1.0);
}

|||

---


#### 000

@@@
{
    "title": "真夏の太陽",
    "author": "doxas",
    "description": "寒いのはきらいです！！"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

const float PI = 3.1415926;
const float PI2 = PI * 2.0;

void main(){
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / min(resolution.x, resolution.y);
    float s = sin((atan(p.y, p.x) + PI) / PI2 * PI * 100.0);
    float t = length(p);
    float q = 1.0 - step(t, 0.5);
    vec3 u = step(t, 0.5) * vec3(1.0, 0.3, 0.0);
    float r = abs(0.01 / (t - 0.5));
    float v = 1.5 / abs(sin(length(p * 50.0) - time * 9.0 + t + s));
    float l = sin(time * 4.0) + 0.8;
    float w = min(time * 0.25 - 0.5, 1.0) * l;
    vec3 dest = vec3(v) * vec3(0.8, 0.3, 0.1) * q + r + u;
    gl_FragColor = vec4(dest * w, 1.0);
}
|||

---


#### 000

@@@
{
    "title": "黒板",
    "author": "s_kimura",
    "description": "普通の線や四角形をどうやって書くのか調べているうちに、こうなりました..."
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D buckbuffer; // previous scene texture

#define Thickness 0.009

float rand(vec2 co){
    return fract(sin(dot(co.xy ,vec2(12.9898,78.233))) * 43758.5453);
}


float drawLine(vec2 p1, vec2 p2) {
  vec2 uv = gl_FragCoord.xy / resolution.xy;

  float a = abs(distance(p1, uv));
  float b = abs(distance(p2, uv));
  float c = abs(distance(p1, p2));

  if ( a >= c || b >=  c ) return 0.0;

  float p = (a + b + c) * 0.5;

  // median to (p1, p2) vector
  float h = 2.0 / c * sqrt( p * ( p - a) * ( p - b) * ( p - c));

  //float n = rand(gl_FragCoord.xy) * 0.03;
  float n = rand(gl_FragCoord.xy * (time * 0.01)) * 0.03;
  // float n = Thickness;
  
  return mix(1.0, 0.0, smoothstep(0.5 * n, 1.5 * 0.5 * n, h));
}

float drawRect(vec2 st, float left, float bottom, float right, float top){
    //Left Bottom
    vec2 rect1 = step(vec2(left,bottom),st);
    float pct = rect1.x * rect1.y;
    
    //Right top
    vec2 rect2 = step(vec2(right,top),1.0 - st);
    pct *= rect2.x * rect2.y;
    return pct;
}

void main(){
  vec4 bgcolor = vec4(0.1, 0.25, 0.0, 1.0);
  
  vec2 st = gl_FragCoord.xy/resolution.xy;
  float pct1 = drawRect(st, 0.75, 0.1, 0.05, 0.8);
  vec4 rect1 = vec4(pct1 * 0.6,pct1 * 0.2,0.0, 1.0);
  
  float pct2 = drawRect(st, 0.83, 0.1, 0.13, 0.8);
  vec4 rect2 = vec4(pct2 * 0.7,pct2 * 0.1,0.0, 1.0);
  
  gl_FragColor = 
  	bgcolor +
  	rect1 +
  	rect2 +
  	vec4(
  		drawLine(vec2(0.35, 0.85), vec2(0.35, 0.7)) +
  		drawLine(vec2(0.35, 0.7), vec2(0.3, 0.8)) +
  		drawLine(vec2(0.3, 0.9), vec2(0.35, 0.95)) +
  		drawLine(vec2(0.35, 0.95), vec2(0.4, 0.9)) +
  		drawLine(vec2(0.3, 0.8), vec2(0.35, 0.85)) +
  		drawLine(vec2(0.35, 0.85), vec2(0.4, 0.8)) +
  		drawLine(vec2(0.4, 0.8), vec2(0.38, 0.7)) +
  		drawLine(vec2(0.4, 0.8), vec2(0.38, 0.7)) +
  		drawLine(vec2(0.55, 0.85), vec2(0.55, 0.7)) +
  		drawLine(vec2(0.55, 0.7), vec2(0.5, 0.8)) +
  		drawLine(vec2(0.5, 0.9), vec2(0.55, 0.95)) +
  		drawLine(vec2(0.55, 0.95), vec2(0.6, 0.9)) +
  		drawLine(vec2(0.5, 0.8), vec2(0.55, 0.85)) +
  		drawLine(vec2(0.55, 0.85), vec2(0.6, 0.8)) +
  		drawLine(vec2(0.6, 0.8), vec2(0.58, 0.7)) +
  		drawLine(vec2(0.6, 0.8), vec2(0.58, 0.7)) +
  		drawLine(vec2(0.45, 0.7), vec2(0.45, 0.55)) +
  		drawLine(vec2(0.45, 0.55), vec2(0.55, 0.55)) +
  		drawLine(vec2(0.4, 0.65), vec2(0.5, 0.66)) +
  		drawLine(vec2(0.4, 0.6), vec2(0.5, 0.59)) +
  		drawLine(vec2(0.35, 0.43), vec2(0.4, 0.5)) +
  		drawLine(vec2(0.4, 0.5), vec2(0.6, 0.43)) +
  		drawLine(vec2(0.2, 0.8), vec2(0.25, 0.4)) +
  		drawLine(vec2(0.27, 0.4), vec2(0.4, 0.3)) +
  		drawLine(vec2(0.4, 0.3), vec2(0.65, 0.35)) +
  		drawLine(vec2(0.68, 0.8), vec2(0.7, 0.7)) +
  		drawLine(vec2(0.73, 0.8), vec2(0.75, 0.73))
  	);
  
}



|||

---


#### 000

@@@
{
    "title": "ワープ",
    "author": "sawa-zen",
    "description": "ワープっぽいのができたのでとりあえず。"
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
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / resolution;
    float c = cos(time);
    float s = sin(time);
    float at = atan(length(p));
    float e = 0.1 / length(p + vec2(c, s)) + time;
    
    float e2 = sin(e * 100.0);
    
    vec3 color = hsv(time, 0.3, 0.8);
    
    gl_FragColor = vec4(vec3(e2 * sin(time * 10.0)) * color, 1.0);
}

|||

---


#### 000

@@@
{
    "title": "hoge",
    "author": "gam0022",
    "description": "適当です"
}
@@@

---

|||
precision highp float;

#extension GL_OES_standard_derivatives : enable

uniform float time;
uniform vec2 mouse;
uniform vec2 resolution;

// consts
const float EPS = 1e-4;
const float OFFSET = EPS * 10.0;
const float PI = 3.14159;
const float INF = 1e+10;

const vec3 lightDir = vec3( -0.48666426339228763, 0.8111071056538127, -0.3244428422615251 );
const vec3 backgroundColor = vec3( 1.0 );
const vec3 gateColor = vec3( 1.0, 1.0, 1.0 );

const float totalTime = 75.0;

// globals
vec3 cPos, cDir;
float normalizedGlobalTime = 0.0;
//vec3 illuminationColor;

struct Intersect {
    bool isHit;

    vec3 position;
    float distance;
    vec3 normal;

    int material;
    vec3 color;
};
    
const int BASIC_MATERIAL = 0;
const int MIRROR_MATERIAL = 1;


// distance functions
vec3 opRep( vec3 p, float interval ) {
    return mod( p, interval ) - 0.5 * interval;
}

vec2 opRep( vec2 p, float interval ) {
    return mod( p, interval ) - 0.5 * interval;
}

float opRep( float x, float interval ) {
    return mod( x, interval ) - 0.5 * interval;
}

float sphereDist( vec3 p, vec3 c, float r ) {
    return length( p - c ) - r;
}

float sdCappedCylinder( vec3 p, vec2 h ) {
    vec2 d = abs(vec2(length(p.xz),p.y)) - h;
    return min(max(d.x,d.y),0.0) + length(max(d,0.0));
}

float udBox( vec3 p, vec3 b )
{
    return length(max(abs(p)-b,0.0));
}

float udFloor( vec3 p ){
    float t1 = 1.0;
    float t2 = 3.0;
    float d = 0.0;
    return dot(p,vec3(0.0,1.0,0.0)) - d;
}

float dGate( vec3 p ) {
    p.y -= 1.3 * 0.5;
    
    float r = 0.05;
    float left  = sdCappedCylinder( p - vec3( -1.0, 0.0, 0.0 ),  vec2(r, 1.3));
    float right = sdCappedCylinder( p - vec3( 1.0,  0.0, 0.0 ),  vec2(r, 1.3));

    float ty = 0.02 * p.x * p.x;
    float tx = 0.5 * ( p.y - 1.3 );
    float katsura  = udBox( p - vec3( 0.0, 1.3 + ty, 0.0 ), vec3( 1.7 + tx, r * 2.0 + ty, r ) );

    float kan = udBox( p - vec3( 0.0, 0.7, 0.0 ), vec3( 1.3, r, r ) );
    float gakuduka = udBox( p - vec3( 0.0, 1.0, 0.0), vec3( r, 0.3, r ) );

    return min( min( left, right ), min( gakuduka, min( katsura, kan ) ) );
}

float dRepGate( vec3 p ) {
    if ( normalizedGlobalTime <= 0.5 ) {
        p.z = opRep( p.z, 1.0 + 20.0 * cos( PI * normalizedGlobalTime ) );
    } else {
        p.xz = opRep( p.xz, 10.0  );
    }
    return dGate( p );
}

float dRepCappedCylinder( vec3 p ) {
    float g = 5.0;
    float a = p.x + p.z + 0.5  * g;
    float tall = cos( floor( a / g ) + time );
    p.xz = opRep( p.xz, g );
    return sdCappedCylinder( p , vec2( 0.5, 3.0 + tall ) );
}

float sceneDistance( vec3 p ) {
    return min(
        udFloor( p ),
        dRepCappedCylinder( p )
    );
}

// color functions
vec3 hsv2rgb( vec3 c ) {

    vec4 K = vec4( 1.0, 2.0 / 3.0, 1.0 / 3.0, 3.0 );
    vec3 p = abs( fract( c.xxx + K.xyz ) * 6.0 - K.www );
    return c.z * mix( K.xxx, clamp( p - K.xxx, 0.0, 1.0 ), c.y );

}

Intersect minIntersect( Intersect a, Intersect b ) {
    if ( a.distance < b.distance ) {
        return a;
    } else {
        return b;
    }
}

Intersect sceneIntersect( vec3 p ) {

    Intersect a;
    a.distance = sceneDistance( p );
    a.material = BASIC_MATERIAL;
    // return minIntersect( a, b );
    return a;
}

vec3 calcNormal( vec3 p ) {
    vec2 e = vec2( 1.0, -1.0 ) * 0.001;
    return normalize(
        e.xyy * sceneDistance( p + e.xyy ) + e.yyx * sceneDistance( p + e.yyx ) + 
        e.yxy * sceneDistance( p + e.yxy ) + e.xxx * sceneDistance( p + e.xxx ) );
}

float calcShadow( vec3 ro, vec3 rd ) {

    float h = 0.0;
    float c = 0.0;
    float r = 1.0;
    float shadowCoef = 0.5;

    for ( float t = 0.0; t < 50.0; t++ ) {

        h = sceneDistance( ro + rd * c );

        if ( h < EPS ) return shadowCoef;

        r = min( r, h * 16.0 / c );
        c += h;

    }

    return 1.0 - shadowCoef + r * shadowCoef;

}


float calcAO(vec3 pos, vec3 normal) {
    float k = 1.0, occluded = 0.0;
    for (int i = 0; i < 5; i++) {
        float length = 1.5 * float(i);
        float distance = sceneDistance(normal * length + pos);
        occluded += (length - distance) * k;
        k *= 0.1;
    }
    return clamp(1.0 - occluded, 0.0, 1.0);
}

Intersect getRayColor( vec3 origin, vec3 ray ) {

    // marching loop
    float d, minDist, trueDepth;
    float distance = 0.0;
    vec3 p = origin;
    int count = 0;
    Intersect nearest;

    // first pass (water)
    for ( int i = 0; i < 120; i++ ){

        d = sceneDistance( p );
        distance += d;
        p = origin + distance * ray;

        count = i;
        if ( abs(d) < EPS ) break;

    }

    if ( abs(d) < EPS ) {

        nearest = sceneIntersect( p );
        nearest.position = p;
        nearest.normal = calcNormal(p);
        nearest.distance = distance;
        float diffuse = clamp( dot( lightDir, nearest.normal ), 0.0, 1.0 );
        float specular = pow( clamp( dot( reflect( lightDir, nearest.normal ), ray ), 0.0, 1.0 ), 6.0 );
        float shadow = calcShadow( p + nearest.normal * OFFSET, lightDir );
    float ao = calcAO( p, nearest.normal );  

        if ( nearest.material == BASIC_MATERIAL ) {
        nearest.color = vec3( 1.0 ) * diffuse * ao * shadow;
        } else if ( nearest.material == MIRROR_MATERIAL ) {
            nearest.color = vec3( 0.7 ) * diffuse + vec3( 1.0 ) * specular;
        }

        nearest.isHit = true;

    } else {

        nearest.color = backgroundColor;
        nearest.isHit = false;

    }
    nearest.color = clamp( nearest.color + 0.01 * nearest.distance, 0.0, 1.0 );

    // second pass (gates)
    /*p = origin;
    distance = 0.0;
    minDist = INF;
    for ( int i = 0; i < 20; i++ ){
        d = dRepGate( p );
        minDist = min(d, minDist);
        //if ( d < minDist ) {
        //    minDist = d;
        //    trueDepth = distance;
        //}
        distance += d;
        p = origin + distance * ray;
        if ( i == 9 && normalizedGlobalTime <= 0.5 ) {
            break;
        }
    }

    if ( abs(d) < EPS ) {
        nearest.color += gateColor;
    } else {
        nearest.color += gateColor * clamp( 0.05 / minDist, 0.0, 1.0 );
    }*/

    return nearest;

}

void main( void ) {
    normalizedGlobalTime = mod( time / totalTime, 1.0 );

    // fragment position
    vec2 p = ( gl_FragCoord.xy * 2.0 - resolution.xy ) / min(  resolution.x,  resolution.y );

    // camera and ray
    //if ( normalizedGlobalTime < 0.7 ) {
    //    cPos = vec3( 0.0, 0.8 + 0.4 * cos( time ), 3.0 * time );
    //    cDir = normalize( vec3( 0.0, -0.1, 1.0 ) );
    //} else {
        cPos = vec3( 0.0, 6.2, 3.0 * time );
        cDir = normalize( vec3( 0.0, -0.3, 1.0 ) );
    //}
    vec3 cSide = normalize( cross( cDir, vec3( 0.0, 1.0 ,0.0 ) ) );
    vec3 cUp   = normalize( cross( cSide, cDir ) );
    float targetDepth = 1.3;
    vec3 ray = normalize( cSide * p.x + cUp * p.y + cDir * targetDepth );

    // Illumination Color
    // illuminationColor = hsv2rgb( vec3( time * 0.02 + 0.6, 1.0, 1.0 ) );

    vec3 color = vec3( 0.0 );
    float alpha = 1.0;
    Intersect nearest;

    for ( int i = 0; i < 3; i++ ) {

        nearest = getRayColor( cPos, ray );

        color += alpha * nearest.color;
        alpha *= 0.5;
        ray = normalize( reflect( ray, nearest.normal ) );
        cPos = nearest.position + nearest.normal * OFFSET;

        if ( !nearest.isHit || nearest.material != MIRROR_MATERIAL ) break;

    }

    gl_FragColor  = vec4(color, 1.0);

}
|||

---


#### 000

@@@
{
    "title": "Retro Hero",
    "author": "AnnPin",
    "description": "GLSLでドット絵作ってみました。"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D buckbuffer; // previous scene texture

const float PI = 3.14159265358979;

float rand(vec2 co){
  return fract(sin(dot(co.xy ,vec2(12.9898,78.233))) * 43758.5453);
}


vec2 getBlockId(vec2 uv, int n) {
    vec2 p = (uv + 1.0) / 2.0;    // (0, 0) -> (1, 1) 正規化
    p = float(n) * p;             // (0, 0) -> (n, n)
    return floor(p);                     // x座標ID, y座標ID
}

float getBlockWidth(int n) {
    return 1.0 / float(n);
}


vec2 getCenterCoordFromId(vec2 blockId, int n) {
    // ID は 0, 1, ..., n - 1
    // (0, 0) -> (1, 1) 正規化が行われている前提で各Block の中心中心座標を返却.
    float blockWidth = getBlockWidth(n);
    vec2 offsets = blockWidth * blockId;
    vec2 center = vec2(blockWidth / 2.0) + offsets;
    
    return center;
}

vec3 getColor(vec2 uv, vec2 center, vec2 blockId, int n) {
    vec2 p = (uv + 1.0) / 2.0;    // (0, 0) -> (1, 1) 正規化
    float intensity = 0.01 / length(p - center);
    return vec3(intensity);
}

float getRed(vec2 blockId) {
    float a = 0.0;
    int xId = int(blockId.x);
    int yId = int(blockId.y);
    
    if (yId == 2) {
        if (xId == 4) {
            a = 1.0;
        } else if (xId == 5) {
            a = 1.0;
        } else if (xId == 6) {
            a = 1.0;	
        } else if (xId == 9) {
            a = 1.0;
        } else if (xId == 10) {
            a = 1.0;
        } else if (xId == 11) {
            a = 1.0;
        }
    } else if (yId == 3) {
        if (xId == 4) {
            a = 1.0;
        } else if (xId == 5) {
            a = 1.0;
        } else if (xId == 6) {
            a = 1.0;
        } else if (xId == 7) {
            a = 1.0;
        } else if (xId == 8) {
            a = 1.0;
        } else if (xId == 9) {
            a = 1.0;
        } else if (xId == 10) {
            a = 1.0;
        } else if (xId == 11) {
            a = 1.0;
        }
    } else if (yId == 4) {
        if (xId == 5) {
            a = 1.0;
        } else if (xId == 6) {
            a = 1.0;
        } else if (xId == 7) {
            a = 1.0;
        } else if (xId == 8) {
            a = 1.0;
        } else if (xId == 9) {
            a = 1.0;
        } else if (xId == 10) {
            a = 1.0;
        }
    } else if (yId == 5) {
        if (xId == 5) {
            a = 1.0;
        } else if (xId == 7) {
            a = 1.0;
        } else if (xId == 8) {
            a = 1.0;
        } else if (xId == 10) {
            a = 1.0;
        }
    } else if (yId == 6) {
        if (xId == 6) {
            a = 1.0;
        } else if (xId == 7) {
            a = 1.0;
        } else if (xId == 8) {
            a = 1.0;
        } else if (xId == 9) {
            a = 1.0;
        }
    } else if (yId == 7) {
        if (xId == 6) {
            a = 1.0;
        } else if (xId == 9) {
            a = 1.0;
        }
    } else if (yId == 8) {
        if (xId == 6) {
            a = 1.0;
        }
    } else if (yId == 14) {
        if (xId == 4) {
            a = 1.0;
        } else if (xId == 5) {
            a = 1.0;
        } else if (xId == 6) {
            a = 1.0;
        } else if (xId == 7) {
            a = 1.0;
        } else if (xId == 8) {
            a = 1.0;
        } else if (xId == 9) {
            a = 1.0;
        } else if (xId == 10) {
            a = 1.0;
        } else if (xId == 11) {
            a = 1.0;
        } else if (xId == 12) {
            a = 1.0;
        }
    } else if (yId == 15) {
        if (xId == 5) {
            a = 1.0;
        } else if (xId == 6) {
            a = 1.0;
        } else if (xId == 7) {
            a = 1.0;
        } else if (xId == 8) {
            a = 1.0;
        } else if (xId == 9) {
            a = 1.0;
        }
    }
    
    return a;
}

float getBrown(vec2 blockId) {
    float a = 0.0;
    int xId = int(blockId.x);
    int yId = int(blockId.y);

    if (yId == 0) {
        if (xId == 2) {
            a = 1.0;
        } else if (xId == 3) {
            a = 1.0;
        } else if (xId == 4) {
            a = 1.0;
        } else if (xId == 5) {
            a = 1.0;
        } else if (xId == 10) {
            a = 1.0;
        } else if (xId == 11) {
            a = 1.0;
        } else if (xId == 12) {
            a = 1.0;
        } else if (xId == 13) {
            a = 1.0;
        }
    } else if (yId == 1) {
        if (xId == 3) {
            a = 1.0;
        } else if (xId == 4) {
            a = 1.0;
        } else if (xId == 5) {
            a = 1.0;
        } else if (xId == 10) {
            a = 1.0;
        } else if (xId == 11) {
            a = 1.0;
        } else if (xId == 12) {
            a = 1.0;
        }
    } else if (yId == 5) {
        if (xId == 4) {
            a = 1.0;
        } else if (xId == 11) {
            a = 1.0;
        }
    } else if (yId == 6) {
        if (xId == 2) {
            a = 1.0;
        } else if (xId == 3) {
            a = 1.0;
        } else if (xId == 4) {
            a = 1.0;
        } else if (xId == 5) {
            a = 1.0;
        } else if (xId == 10) {
            a = 1.0;
        } else if (xId == 11) {
            a = 1.0;
        } else if (xId == 12) {
            a = 1.0;
        } else if (xId == 13) {
            a = 1.0;
        }
    } else if (yId == 7) {
        if (xId == 3) {
            a = 1.0;
        } else if (xId == 4) {
            a = 1.0;
        } else if (xId == 5) {
            a = 1.0;
        } else if (xId == 7) {
            a = 1.0;
        } else if (xId == 8) {
            a = 1.0;
        } else if (xId == 10) {
            a = 1.0;
        } else if (xId == 11) {
            a = 1.0;
        } else if (xId == 12) {
            a = 1.0;
        }
    } else if (yId == 8) {
        if (xId == 4) {
            a = 1.0;
        } else if (xId == 5) {
            a = 1.0;
        } else if (xId == 7) {
            a = 1.0;
        } else if (xId == 8) {
            a = 1.0;
        } else if (xId == 9) {
            a = 1.0;
        }
    } else if (yId == 10) {
        if (xId == 3) {
            a = 1.0;
        } else if (xId == 4) {
            a = 1.0;
        } else if (xId == 9) {
            a = 1.0;
        } else if (xId == 10) {
            a = 1.0;
        } else if (xId == 11) {
            a = 1.0;
        } else if (xId == 12) {
            a = 1.0;
        }
    } else if (yId == 11) {
        if (xId == 3) {
            a = 1.0;
        } else if (xId == 5) {
            a = 1.0;
        } else if (xId == 6) {
            a = 1.0;
        } else if (xId == 10) {
            a = 1.0;
        }
    } else if (yId == 12) {
        if (xId == 3) {
            a = 1.0;
        } else if (xId == 5) {
            a = 1.0;
        } else if (xId == 9) {
            a = 1.0;
        }
    } else if (yId == 13) {
        if (xId == 4) {
            a = 1.0;
        } else if (xId == 5) {
            a = 1.0;
        } else if (xId == 6) {
            a = 1.0;
        } else if (xId == 9) {
            a = 1.0;
        }
    }
        
    return a;
}

float getOrange(vec2 blockId) {
    float a = 0.0;
    int xId = int(blockId.x);
    int yId = int(blockId.y);

    if (yId == 3) {
        if (xId == 2) {
            a = 1.0;
        } else if (xId == 3) {
            a = 1.0;
        } else if (xId == 12) {
            a = 1.0;
        } else if (xId == 13) {
            a = 1.0;
        }
    } else if (yId == 4) {
        if (xId == 2) {
            a = 1.0;
        } else if (xId == 3) {
            a = 1.0;
        } else if (xId == 4) {
            a = 1.0;
        } else if (xId == 11) {
            a = 1.0;
        } else if (xId == 12) {
            a = 1.0;
        } else if (xId == 13) {
            a = 1.0;
        }
    } else if (yId == 5) {
        if (xId == 2) {
            a = 1.0;
        } else if (xId == 3) {
            a = 1.0;
        } else if (xId == 6) {
            a = 1.0;
        } else if (xId == 9) {
            a = 1.0;
        } else if (xId == 12) {
            a = 1.0;
        } else if (xId == 13) {
            a = 1.0;
        }
    } else if (yId == 9) {
        if (xId == 5) {
            a = 1.0;
        } else if (xId == 6) {
            a = 1.0;
        } else if (xId == 7) {
            a = 1.0;
        } else if (xId == 8) {
            a = 1.0;
        } else if (xId == 9) {
            a = 1.0;
        } else if (xId == 10) {
            a = 1.0;
        } else if (xId == 11) {
            a = 1.0;
        }
    } else if (yId == 10) {
        if (xId == 5) {
            a = 1.0;
        } else if (xId == 6) {
            a = 1.0;
        } else if (xId == 7) {
            a = 1.0;
        } else if (xId == 8) {
            a = 1.0;
        }
    } else if (yId == 11) {
        if (xId == 4) {
            a = 1.0;
        } else if (xId == 7) {
            a = 1.0;
        } else if (xId == 8) {
            a = 1.0;
        } else if (xId == 9) {
            a = 1.0;
        } else if (xId == 11) {
            a = 1.0;
        } else if (xId == 12) {
            a = 1.0;
        } else if (xId == 13) {
            a = 1.0;
        }
    } else if (yId == 12) {
        if (xId == 4) {
            a = 1.0;
        } else if (xId == 6) {
            a = 1.0;
        } else if (xId == 7) {
            a = 1.0;
        } else if (xId == 8) {
            a = 1.0;
        } else if (xId == 10) {
            a = 1.0;
        } else if (xId == 11) {
            a = 1.0;
        } else if (xId == 12) {
            a = 1.0;
        }
    } else if (yId == 13) {
        if (xId == 7) {
            a = 1.0;
        } else if (xId == 8) {
            a = 1.0;
        } else if (xId == 10) {
            a = 1.0;
        }
    }
    
    return a;
}

vec3 getMario(vec2 blockId) {
    vec3 RED    = vec3(206.0 / 255.0,  13.0 / 255.0,  4.0 / 255.0);
    vec3 BROWN  = vec3(126.0 / 255.0,  91.0 / 255.0,  1.0 / 255.0);
    vec3 ORANGE = vec3(253.0 / 255.0, 168.0 / 255.0, 29.0 / 255.0);
    
    vec3 color = vec3(0.0, 0.0, 0.0);
    
    color = mix(color, RED,    getRed(blockId));
    color = mix(color, BROWN,  getBrown(blockId));
    color = mix(color, ORANGE, getOrange(blockId));
    
    return color;
}

float getCircleIntensity(vec2 uv, vec2 center, vec2 blockId, int n) {
    vec2 p = (uv + 1.0) / 2.0;    // (0, 0) -> (1, 1) 正規化
    float coefficient = 0.025 * (sin(2.0 * time) + 1.0 + 0.25) / 2.0;
    float intensity = coefficient / length(p - center);
    return intensity;
}


void main(){
    vec2 uv = (2.0 * gl_FragCoord.xy - resolution.xy) / min(resolution.x, resolution.y);
    int blockNum = 16;
    vec2 blockId = getBlockId(uv, blockNum);
    
    // 座標変換
    mat2 rot = mat2(cos(time - mod(0.25 * time, 2.0*PI)), -sin(time - mod(0.25 * time, 2.0*PI)), 
                    sin(time - mod(0.25 * time, 2.0*PI)),  cos(time - mod(0.25 * time, 2.0*PI)));
    uv = rot   * uv;
    // ブロックID の再取得
    blockId = getBlockId(uv, blockNum);
    

    vec3 mario = getMario(blockId);
    
    vec2 center = getCenterCoordFromId(blockId, blockNum);
    float circleIntensity = getCircleIntensity(uv, center, blockId, blockNum);
    
    vec3 color = mario * circleIntensity;
    
    vec2 pos = uv;
    pos *= sin(time);
    float r = rand(pos);

    vec3 noise = vec3(r);
    float noise_intensity = (sin(2.0 * time) + 1.0) / 2.0;

    vec3 finalColor = mix(color, noise, noise_intensity);
    
    gl_FragColor = vec4(finalColor, 1.0);
}

|||

---


#### 000

@@@
{
    "title": "Shinto Shrine Archway",
    "author": "gam0022",
    "description": "先週くらいにShadertoyに投稿したのをポート！\nhttps://www.shadertoy.com/view/XttSWN"
}
@@@

---

|||
#ifdef GL_ES
precision mediump float;
#endif

#extension GL_OES_standard_derivatives : enable

uniform float time;
uniform vec2 mouse;
uniform vec2 resolution;

// consts
const float EPS = 1e-4;
const float OFFSET = EPS * 10.0;
const float PI = 3.14159;
const float INF = 1e+10;

const vec3 lightDir = vec3( -0.48666426339228763, 0.8111071056538127, -0.3244428422615251 );
const vec3 backgroundColor = vec3( 0.0 );
const vec3 gateColor = vec3( 1.0, 0.1, 0.1 );

const float totalTime = 75.0;

// globals
vec3 cPos, cDir;
float normalizedGlobalTime = 0.0;
//vec3 illuminationColor;

struct Intersect {
    bool isHit;

    vec3 position;
    float distance;
    vec3 normal;

    int material;
    vec3 color;
};
    
const int BASIC_MATERIAL = 0;
const int MIRROR_MATERIAL = 1;


// distance functions
vec3 opRep( vec3 p, float interval ) {
    return mod( p, interval ) - 0.5 * interval;
}

vec2 opRep( vec2 p, float interval ) {
    return mod( p, interval ) - 0.5 * interval;
}

float opRep( float x, float interval ) {
    return mod( x, interval ) - 0.5 * interval;
}

float sphereDist( vec3 p, vec3 c, float r ) {
    return length( p - c ) - r;
}

float sdCappedCylinder( vec3 p, vec2 h ) {
    vec2 d = abs(vec2(length(p.xz),p.y)) - h;
    return min(max(d.x,d.y),0.0) + length(max(d,0.0));
}

float udBox( vec3 p, vec3 b )
{
    return length(max(abs(p)-b,0.0));
}

float udFloor( vec3 p ){
    float t1 = 1.0;
    float t2 = 3.0;
    float d = -0.5;
    for( float i = 0.0; i < 3.0; i++ ) {
        float f = pow( 2.0, i );
    	d += 0.1 / f * ( sin( f * t1 * p.x + t2 * time ) + sin( f * t1 * p.z + t2 * time ) );
    }
    return dot(p,vec3(0.0,1.0,0.0)) - d;
}

float dGate( vec3 p ) {
    p.y -= 1.3 * 0.5;
    
    float r = 0.05;
    float left  = sdCappedCylinder( p - vec3( -1.0, 0.0, 0.0 ),  vec2(r, 1.3));
    float right = sdCappedCylinder( p - vec3( 1.0,  0.0, 0.0 ),  vec2(r, 1.3));

    float ty = 0.02 * p.x * p.x;
    float tx = 0.5 * ( p.y - 1.3 );
    float katsura  = udBox( p - vec3( 0.0, 1.3 + ty, 0.0 ), vec3( 1.7 + tx, r * 2.0 + ty, r ) );

    float kan = udBox( p - vec3( 0.0, 0.7, 0.0 ), vec3( 1.3, r, r ) );
    float gakuduka = udBox( p - vec3( 0.0, 1.0, 0.0), vec3( r, 0.3, r ) );

    return min( min( left, right ), min( gakuduka, min( katsura, kan ) ) );
}

float dRepGate( vec3 p ) {
    if ( normalizedGlobalTime <= 0.5 ) {
        p.z = opRep( p.z, 1.0 + 20.0 * cos( PI * normalizedGlobalTime ) );
    } else {
        p.xz = opRep( p.xz, 10.0  );
    }
    return dGate( p );
}

float sceneDistance( vec3 p ) {
    return udFloor( p );
}


// color functions
vec3 hsv2rgb( vec3 c ) {

    vec4 K = vec4( 1.0, 2.0 / 3.0, 1.0 / 3.0, 3.0 );
    vec3 p = abs( fract( c.xxx + K.xyz ) * 6.0 - K.www );
    return c.z * mix( K.xxx, clamp( p - K.xxx, 0.0, 1.0 ), c.y );

}

Intersect minIntersect( Intersect a, Intersect b ) {
    if ( a.distance < b.distance ) {
        return a;
    } else {
        return b;
    }
}

Intersect sceneIntersect( vec3 p ) {

    Intersect a;
    a.distance = udFloor( p );
    a.material = MIRROR_MATERIAL;
    // return minIntersect( a, b );
    return a;
}

vec3 getNormal( vec3 p ) {
    vec2 e = vec2( 1.0, -1.0 ) * 0.001;
    return normalize(
        e.xyy * sceneDistance( p + e.xyy ) + e.yyx * sceneDistance( p + e.yyx ) + 
        e.yxy * sceneDistance( p + e.yxy ) + e.xxx * sceneDistance( p + e.xxx ) );
}

float getShadow( vec3 ro, vec3 rd ) {

    float h = 0.0;
    float c = 0.0;
    float r = 1.0;
    float shadowCoef = 0.5;

    for ( float t = 0.0; t < 50.0; t++ ) {

        h = sceneDistance( ro + rd * c );

        if ( h < EPS ) return shadowCoef;

        r = min( r, h * 16.0 / c );
        c += h;

    }

    return 1.0 - shadowCoef + r * shadowCoef;

}

Intersect getRayColor( vec3 origin, vec3 ray ) {

    // marching loop
    float d, minDist, trueDepth;
    float distance = 0.0;
    vec3 p = origin;
    int count = 0;
    Intersect nearest;

    // first pass (water)
    for ( int i = 0; i < 120; i++ ){

        d = sceneDistance( p );
        distance += d;
        p = origin + distance * ray;

        count = i;
        if ( abs(d) < EPS ) break;

    }

    if ( abs(d) < EPS ) {

        nearest = sceneIntersect( p );
        nearest.position = p;
        nearest.normal = getNormal(p);
        nearest.distance = distance;
        float diffuse = clamp( dot( lightDir, nearest.normal ), 0.1, 1.0 );
        float specular = pow( clamp( dot( reflect( lightDir, nearest.normal ), ray ), 0.0, 1.0 ), 6.0 );
        //float shadow = getShadow( p + nearest.normal * OFFSET, lightDir );

        if ( nearest.material == BASIC_MATERIAL ) {
        } else if ( nearest.material == MIRROR_MATERIAL ) {
            nearest.color = vec3( 0.5, 0.7, 0.8 ) * diffuse + vec3( 1.0 ) * specular;
        }

        nearest.isHit = true;

    } else {

        nearest.color = backgroundColor;
        nearest.isHit = false;

    }
    nearest.color = clamp( nearest.color - 0.1 * nearest.distance, 0.0, 1.0 );

    // second pass (gates)
    p = origin;
    distance = 0.0;
    minDist = INF;
    for ( int i = 0; i < 20; i++ ){
        d = dRepGate( p );
        minDist = min(d, minDist);
        /*if ( d < minDist ) {
            minDist = d;
            trueDepth = distance;
        }*/
        distance += d;
        p = origin + distance * ray;
        if ( i == 9 && normalizedGlobalTime <= 0.5 ) {
            break;
        }
    }

    if ( abs(d) < EPS ) {
        nearest.color += gateColor;
    } else {
        nearest.color += gateColor * clamp( 0.05 / minDist, 0.0, 1.0 );
    }

    return nearest;

}

void main( void ) {
    normalizedGlobalTime = mod( time / totalTime, 1.0 );

    // fragment position
    vec2 p = ( gl_FragCoord.xy * 2.0 - resolution.xy ) / min(  resolution.x,  resolution.y );

    // camera and ray
    if ( normalizedGlobalTime < 0.7 ) {
        cPos = vec3( 0.0, 0.6 + 0.4 * cos( time ), 3.0 * time );
        cDir = normalize( vec3( 0.0, -0.1, 1.0 ) );
    } else {
        cPos = vec3( 0.0, 0.6 + 0.4 * cos( time ) + 50.0 * ( normalizedGlobalTime - 0.7 ), 3.0 * time );
        cDir = normalize( vec3( 0.0, -0.1 - ( normalizedGlobalTime - 0.7 ), 1.0 ) );
    }
    vec3 cSide = normalize( cross( cDir, vec3( 0.0, 1.0 ,0.0 ) ) );
    vec3 cUp   = normalize( cross( cSide, cDir ) );
    float targetDepth = 1.3;
    vec3 ray = normalize( cSide * p.x + cUp * p.y + cDir * targetDepth );

    // Illumination Color
    // illuminationColor = hsv2rgb( vec3( time * 0.02 + 0.6, 1.0, 1.0 ) );

    vec3 color = vec3( 0.0 );
    float alpha = 1.0;
    Intersect nearest;

    for ( int i = 0; i < 3; i++ ) {

        nearest = getRayColor( cPos, ray );

        color += alpha * nearest.color;
        alpha *= 0.5;
        ray = normalize( reflect( ray, nearest.normal ) );
        cPos = nearest.position + nearest.normal * OFFSET;

        if ( !nearest.isHit || nearest.material != MIRROR_MATERIAL ) break;

    }

    gl_FragColor  = vec4(color, 1.0);

}
|||

---


#### 000

@@@
{
    "title": "Bubble Gems",
    "author": "tomoyuki710",
    "description": " "
}
@@@

---

|||
#ifdef GL_ES
precision highp float;
#endif

uniform float time;
uniform vec2 resolution;

#define ITE_MAX 150

#define EPS 0.005
#define FAR 10.0
#define V vec2(0.,1.)
#define INIT_LEN 0.01

mat2 rot2(float radian) {
    float c = cos(radian);
    float s = sin(radian);
    
    return mat2(c, s, -s, c);
}

vec3 rotHue(vec3 p, float a){
    vec2 cs = sin(vec2(1.570796, 0) + a);
    mat3 hr = mat3(0.299,  0.587,  0.114,  0.299,  0.587,  0.114,  0.299,  0.587,  0.114) +
        	  mat3(0.701, -0.587, -0.114, -0.299,  0.413, -0.114, -0.300, -0.588,  0.886) * cs.x +
        	  mat3(0.168,  0.330, -0.497, -0.328,  0.035,  0.292,  1.250, -1.050, -0.203) * cs.y;
    return clamp(p * hr, 0.0, 1.0);
}

// ------
// http://www.viz.tamu.edu/faculty/ergun/research/implicitmodeling/papers/sm99.pdf

vec3 n1 = vec3(1.000, 0.000, 0.000);
vec3 n2 = vec3(0.000, 1.000, 0.000);
vec3 n3 = vec3(0.000, 0.000, 1.000);
vec3 n4 = vec3(0.577, 0.577, 0.577);
vec3 n5 = vec3(-0.577, 0.577, 0.577);
vec3 n6 = vec3(0.577, -0.577, 0.577);
vec3 n7 = vec3(0.577, 0.577, -0.577);
vec3 n8 = vec3(0.000, 0.357, 0.934);
vec3 n9 = vec3(0.000, -0.357, 0.934);
vec3 n10 = vec3(0.934, 0.000, 0.357);
vec3 n11 = vec3(-0.934, 0.000, 0.357);
vec3 n12 = vec3(0.357, 0.934, 0.000);
vec3 n13 = vec3(-0.357, 0.934, 0.000);
vec3 n14 = vec3(0.000, 0.851, 0.526);
vec3 n15 = vec3(0.000, -0.851, 0.526);
vec3 n16 = vec3(0.526, 0.000, 0.851);
vec3 n17 = vec3(-0.526, 0.000, 0.851);
vec3 n18 = vec3(0.851, 0.526, 0.000);
vec3 n19 = vec3(-0.851, 0.526, 0.000);

// p as usual, e exponent (p in the paper), r radius or something like that
float cube(vec3 p, float e, float r) {
    float s = pow(abs(dot(p, n1)), e);
    s += pow(abs(dot(p, n2)), e);
    s += pow(abs(dot(p, n3)), e);
    s = pow(s, 1./e);
    return s-r;
}

float octahedral(vec3 p, float e, float r) {
    float s = pow(abs(dot(p, n4)), e);
    s += pow(abs(dot(p, n5)), e);
    s += pow(abs(dot(p, n6)), e);
    s += pow(abs(dot(p, n7)), e);
    s = pow(s, 1./e);
    return s-r;
}

float dodecahedral(vec3 p, float e, float r) {
    float s = pow(abs(dot(p, n14)), e);
    s += pow(abs(dot(p, n15)), e);
    s += pow(abs(dot(p, n16)), e);
    s += pow(abs(dot(p, n17)), e);
    s += pow(abs(dot(p, n18)), e);
    s += pow(abs(dot(p, n19)), e);
    s = pow(s, 1./e);
    return s-r;
}

float icosahedral(vec3 p, float e, float r) {
    float s = pow(abs(dot(p, n4)), e);
    s += pow(abs(dot(p, n5)), e);
    s += pow(abs(dot(p, n6)), e);
    s += pow(abs(dot(p, n7)), e);
    s += pow(abs(dot(p, n8)), e);
    s += pow(abs(dot(p, n9)), e);
    s += pow(abs(dot(p, n10)), e);
    s += pow(abs(dot(p, n11)), e);
    s += pow(abs(dot(p, n12)), e);
    s += pow(abs(dot(p, n13)), e);
    s = pow(s, 1./e);
    return s-r;
}

#define CUBE_RADIUS 0.162
#define CUBE_COEF_MIN 2.0
#define CUBE_COEF_MAX 15.0
#define OCTA_RADIUS 0.158
#define OCTA_COEF_MIN 2.0
#define OCTA_COEF_MAX 18.0
#define DODECA_RADIUS 0.19
#define DODECA_COEF_MIN 3.0
#define DODECA_COEF_MAX 40.0
#define ICOSA_RADIUS 0.2
#define ICOSA_COEF_MIN 5.0
#define ICOSA_COEF_MAX 50.0

#define TIME_COEF 0.9
#define ROTATE_COEF 1.0

#define OBJ_DIST_X 0.7
#define HALF_OBJ_DIST_X OBJ_DIST_X*0.5
#define OBJ_DIST_Y 0.7
#define HALF_OBJ_DIST_Y OBJ_DIST_Y*0.5

float distanceFromCenter;

float dfScene(vec3 _p) {
    	float yIndex = floor(mod(floor((abs(_p.y) + HALF_OBJ_DIST_Y) / OBJ_DIST_Y), 4.0));
    float dist = 0.;

    _p.x += HALF_OBJ_DIST_X * (yIndex + 1.0);
    	_p.y += HALF_OBJ_DIST_Y;
    	vec3 p = vec3(mod(_p.x, OBJ_DIST_X) - HALF_OBJ_DIST_X, mod(_p.y, OBJ_DIST_Y) - HALF_OBJ_DIST_Y, _p.z);
    
     	p.zx = rot2(time * ROTATE_COEF) * p.zx;

    float c = cos(time * TIME_COEF + _p.y * 2.0);
    float mixCoef = c * 0.5 + 0.5;
    
    if (yIndex == 0.0) {
        float coef = mix(ICOSA_COEF_MIN, ICOSA_COEF_MAX, mixCoef);     
    		dist = icosahedral(p, coef, ICOSA_RADIUS);
    } else if (yIndex <= 1.0 && _p.y > 0.0){
        float coef = mix(OCTA_COEF_MIN, OCTA_COEF_MAX, mixCoef);
     		dist = octahedral(p, coef, OCTA_RADIUS);
    }  else if (yIndex <= 1.0) {
        float coef = mix(DODECA_COEF_MIN, DODECA_COEF_MAX, mixCoef);
     		dist = dodecahedral(p, coef, DODECA_RADIUS);
    }  else {
        float coef = mix(CUBE_COEF_MIN, CUBE_COEF_MAX, mixCoef);
     		dist = cube(p, coef, CUBE_RADIUS);
    } 
    
    	distanceFromCenter = length(p);

    	return dist;
}

vec3 surfaceNormal(in vec3 _p) {
    vec2 d = V * 1E-2;
    return normalize(vec3(dfScene(_p + d.yxx) - dfScene(_p - d.yxx),
                  dfScene(_p + d.xyx) - dfScene(_p - d.xyx),
                  dfScene(_p + d.xxy) - dfScene(_p - d.xxy)));
}

vec3 marchScene(vec3 ro, vec3 rd) {
    vec3 pixelColor = vec3(0.0);
    float dist = 0.0;
    vec3 rayPosition = vec3(0.0);
   
    vec3 lightPosition = normalize(vec3(2.0, 5.0, -3.0));
    vec3 sceneColor = rotHue(vec3(0.5, 0.2, 0.8), mod(time / 3.0 + ro.y * 100.0, 6.283));

    for (int i = 0; i < ITE_MAX; i++) {
        rayPosition = ro + rd * dist;
        float ns = dfScene(rayPosition);
        dist += ns;
        if (ns < EPS || dist > FAR) break;
    }
    
    if (dist < FAR) {
        vec3 normalVector = surfaceNormal(rayPosition);

        float g = distanceFromCenter;
        g /= ICOSA_RADIUS;
        g *= 1.35;
        pixelColor = sceneColor * exp(g * g) * 0.05; // 中心から遠くなるほど明るくする

        float spe = pow(max(dot(reflect(rd, normalVector), lightPosition), 0.0), 16.0); // スペキュラ
        pixelColor += spe * vec3(1.0);
    }
    
    return pixelColor;
}
    
void main() {
    vec2 uv = (gl_FragCoord.xy / resolution.xy) * 2.0 - 1.0;
    
    float aspect = resolution.x / resolution.y;
    vec3 dir = normalize(vec3(uv * vec2(aspect, 1.0), 1.0));
    
    vec3 pos = vec3(0.0, 0.0, -1.0);
    
    float rayLen = INIT_LEN; // 探索レイの長さ
    	vec3 rayPos = pos + rayLen * dir; // 探索レイの位置

    vec3 col = marchScene(rayPos, dir);

    gl_FragColor = vec4(col, 1.0);
}

|||

---


#### 000

@@@
{
    "title": "test[ray marching]",
    "author": "ndm",
    "description": "test[ray marching]"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
//uniform sampler2D backbuffer; // previous scene texture

float distanceFunction (vec3 pos) {
    return length(pos) - 1.0;
}

vec3 getNormal(vec3 p) {
    const float d = 0.001;
    return
        normalize (
            vec3 (
                distanceFunction(p + vec3(d, 0.0, 0.0)) - distanceFunction(p + vec3(-d, 0.0, 0.0)),
                distanceFunction(p + vec3(0.0, d, 0.0)) - distanceFunction(p + vec3(0.0, -d, 0.0)),
                distanceFunction(p + vec3(0.0, 0.0, d)) - distanceFunction(p + vec3(0.0, 0.0, -d))
                )
        );
}

void main () {
    
    vec2 pos = (gl_FragCoord.xy*2.0 - resolution) / resolution.y;
    
    vec3 cPos = vec3(0.0, 0.0, 3.0);
    vec3 cDir = vec3(0.0, 0.0, -1.0);
    vec3 cUp = vec3(0.0, 1.0, 0.0) + sin(time) * 50.0;
    vec3 cSide = cross(cDir, cUp);
    float focus = 2.0;
    
    vec3 rayDir = normalize(cSide*pos.x + cUp*pos.y + cDir*focus);
    
    float t = 0.001, d;
    vec3 posOnRay = cPos;
    
    for (int i=0; i<16; ++i) {
        d = distanceFunction (posOnRay);
        t += d;
        posOnRay = cPos + t*rayDir;
    }
    
    vec3 normal = getNormal(posOnRay);
    if (abs(d) < 0.0001){
        gl_FragColor = vec4(normal, 1.0);
    } else {
        gl_FragColor = vec4(0.0);		
    }
    
}
|||

---

#### 000

@@@
{
    "title": "be dazzled by a glare",
    "author": "phoooutty",
    "description": "揺れる電球に目がくらむイメージです。\n本日初めてGLSLに触った初心者なので、しょぼいですが…"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

float lamp(vec2 p) {
    float coef = abs(sin(time) * sin(time));
    
    float x = cos(time) * 0.8;
    float y = abs(coef) - 1.0;
    // length -> ベクトルの長さを得るメソッド
    return (0.2 * coef) / length(p + vec2(x, y));
}

float waves(vec2 p)
{
  return sin(length(p) + time * 2.0);
}

void main(){
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / resolution; // (-512 ~ 512) / 512 -> -1.0 ~ 1.0
    
    float f_lamp = lamp(p);
    vec4 lamp = vec4(vec3(f_lamp, f_lamp * 0.5, 0), 1.0);
    
    
    float f_wave = waves(p);
    vec4 wave = vec4(
    	f_wave * tan(time) * 0.4, 
    	f_wave * tan(time) * 0.2,
    	0, 0.0);
    
    gl_FragColor = lamp + wave;
}

|||

---


#### 000

@@@
{
    "title": "せっかくなので",
    "author": "combat_etizen",
    "description": "とりあえずいろいろ入れてみた"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

const float PI  = 3.1415926;
const float PI2 = PI*2.0;

void main(){
    vec2 p  = (gl_FragCoord.xy * 2.0 - resolution) / resolution;
    vec2 m = mouse * 2.0 - 1.0;
    vec2 offset = vec2(sin(time / 2.0), cos(time / 2.0));
    vec2 v = p + offset;
    
    
    float a = ((atan(v.y, v.x) + PI) / PI2);
    float r = sin(time/1.0) / length(p);
    float g = sin(time/2.0) / length(p);
    float b = sin(time/3.0) / length(p);
    
    float f =  0.5 / length(p-m);
    vec3 col = vec3(r*a,g*a,b*a) * f;

    gl_FragColor = vec4(col, 1.0);
}

|||

---


#### 000

@@@
{
    "title": "noise & orb",
    "author": "P5Aholic",
    "description": "すみません、前に作ったやつの派生版です・・・"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

const int oct   = 4;
const float per = 0.8;
const float map = 100.0;
const float PI  = 3.1415926;

float interpolate(float a, float b, float x){
    float f = x * x * x * (10.0 + x * (-15.0 + 6.0 * x));
    return a * (1.0 - f) + b * f;
}

float rnd(vec2 p){
    return fract(sin(dot(p ,vec2(12.9898,78.233))) * 43758.5453);
}

float irnd(vec2 p){
    vec2 i = floor(p);
    vec2 f = fract(p);
    vec4 v = vec4(rnd(vec2(i.x,       i.y      )),
                  rnd(vec2(i.x + 1.0, i.y      )),
                  rnd(vec2(i.x,       i.y + 1.0)),
                  rnd(vec2(i.x + 1.0, i.y + 1.0)));
    return interpolate(interpolate(v.x, v.y, f.x), interpolate(v.z, v.w, f.x), f.y);
}

float noise(vec2 p){
    float t = 0.0;
    for(int i = 0; i < oct; i++){
        float freq = pow(2.0, float(i));
        float amp  = pow(per, float(oct - i));
        t += irnd(vec2(p.x / freq, p.y / freq)) * amp;
    }
    return t;
}

float snoise(vec2 p, vec2 q, vec2 r){
    return noise( vec2(p.x,       p.y      ) ) *        q.x  *        q.y  +
           noise( vec2(p.x,       p.y + r.y) ) *        q.x  * (1.0 - q.y) +
           noise( vec2(p.x + r.x, p.y      ) ) * (1.0 - q.x) *        q.y  +
           noise( vec2(p.x + r.x, p.y + r.y) ) * (1.0 - q.x) * (1.0 - q.y);
}

void main() {
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / min(resolution.x, resolution.y);
    
    float orb = (0.08 + 0.05 * abs(sin(time))) / (length(p) - 0.6);
    orb += 0.2 / length(p);
    orb = pow(orb, 3.0);
    
    vec2 nc = vec2(0.3 * cos(time * 0.5), 0.0);
    vec2 cp = vec2(atan(p.x - nc.x, p.y - nc.y) / 6.2832, length(p - nc));
    
    vec2 t = mod(cp * map + vec2(0.0, -time * 8.0), map);
    float noise = snoise(t, t / map, vec2(map));
    
    gl_FragColor = vec4(vec3(orb * noise), 1.0) + vec4(0.02, 0.08, 0.15, 1.0);
}
|||

---


#### 000

@@@
{
    "title": "✿",
    "author": "rootx",
    "description": "歯車にしたかったです＞＜；"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D buckbuffer; // previous scene texture


const float PI = 3.1415926535897932384626433832795;
const float PI2 = PI * 2.0;
const float PI_2 = 1.57079632679489661923;
const float PI_4 = 0.785398163397448309616;


float sampleF(vec2 pp, vec2 p, float size, float angle)
{
    const float teeth = 5.0;

    pp -= p;
    float r = length(pp);
    float a = atan(pp.y, pp.x) + angle;

    float phase = fract(0.5/PI * float(teeth) * a);
    float height = 2.0 * abs(phase - 0.5);
    float rad = size * clamp(height / 0.8, -1.0, +1.0);
    float body = 1.0 - step(rad, r);

    float c = body;
    return c;
}

void main(){
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / min(resolution.x, resolution.y);
    float r = length(p);
    float a = atan(p.y, p.x);
    
    
    float rotAngle = PI2 * (10.0 + (time / 5.0));
    float g = 2.0 - 10.0 * fract(time / 10.0);
    vec2 p1 = vec2(0.3, 0.2 * g);
    vec2 p2 = vec2(-0.3, -0.4 + 0.3 * g);
    vec2 p3 = vec2(0.59, 0.2 + 0.8 * g);
    vec2 p4 = vec2(-0.77, 0.25 + 0.4 * g);
    vec2 p5 = vec2(0.9, 0.0 + 0.2 * g);
    float c1 = sampleF(p1, p, 0.3 + 0.06*(0.2* sin(time) + 0.5), rotAngle);
    float c2 = sampleF(p2, p, 0.4 + 0.04*(0.2* sin(time)), rotAngle);
    float c3 = sampleF(p3, p, 0.45 + 0.1*(0.2* sin(time)), rotAngle);
    float c4 = sampleF(p4, p, 0.4 + 0.04*(0.2* sin(time)), rotAngle);
    float c5 = sampleF(p5, p, 0.45 + 0.1*(0.2* sin(time)), rotAngle);
    vec3 color =  c1 * vec3(1.0, 0.97, 0.25 + 0.1 * cos(time))
                + c2 * vec3(1.0, 0.97, 0.25 + 0.1 * cos(time + PI))
                + c3 * vec3(1.0, 0.97, 0.25 + 0.1 * cos(time + PI_4))
                + c4 * vec3(1.0, 0.97, 0.25 + 0.1 * cos(time + PI))
                + c5 * vec3(1.0, 0.97, 0.25 + 0.1 * cos(time + PI_4));
    
    gl_FragColor = vec4(color, 1.0);
}

|||

---


#### 000

@@@
{
    "title": "エメラルド",
    "author": "baco16g",
    "description": "レイマーチングに取り組んだ"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)

const vec3 baseColor = vec3(0.1, 1.0, 0.2);
const vec3 compleColor = vec3(0.5, 0.2, 0.5);

//***********************
//  lib function
//***********************

//　rotate
vec3 rotate(vec3 p, float angle, vec3 axis){
  vec3 a = normalize(axis);
  float s = sin(angle);
  float c = cos(angle);
  float r = 1.0 - c;
  mat3 m = mat3(
      a.x * a.x * r + c,
      a.y * a.x * r + a.z * s,
      a.z * a.x * r - a.y * s,
      a.x * a.y * r - a.z * s,
      a.y * a.y * r + c,
      a.z * a.y * r + a.x * s,
      a.x * a.z * r + a.y * s,
      a.y * a.z * r - a.x * s,
      a.z * a.z * r + c
  );
  return m * p;
}

// cube
float cube(vec3 p) {
  vec3 q = rotate(abs(p), radians(time * 100.0), vec3(0.1, 0.4, 0.3));
  return length(max(q - vec3(0.4, 0.8, 0.4), 0.0));
}

// distance root
float distanceRoot(vec3 p){
  return cube(p);
}

// normal
vec3 genNormal(vec3 p){
  float d = 0.001;
  return normalize(vec3(
    distanceRoot(p + vec3(  d, 0.0, 0.0)) - distanceRoot(p + vec3( -d, 0.0, 0.0)),
    distanceRoot(p + vec3(0.0,   d, 0.0)) - distanceRoot(p + vec3(0.0,  -d, 0.0)),
    distanceRoot(p + vec3(0.0, 0.0,   d)) - distanceRoot(p + vec3(0.0, 0.0,  -d))
  ));
}

// 2D Random
float random (in vec2 st) {
  return fract(sin(dot(st.xy, vec2(12.9898,78.233))) * 43758.5453123);
}

// 2D Noise based on Morgan McGuire @morgan3d
// https://www.shadertoy.com/view/4dS3Wd
float noise (in vec2 st) {
  vec2 i = floor(st);
  vec2 f = fract(st);

  // Four corners in 2D of a tile
  float a = random(i);
  float b = random(i + vec2(1.0, 0.0));
  float c = random(i + vec2(0.0, 1.0));
  float d = random(i + vec2(1.0, 1.0));

  // Smooth Interpolation

  // Cubic Hermine Curve.  Same as SmoothStep()
  vec2 u = f*f*(3.0-2.0*f);
  // u = smoothstep(0.,1.,f);

  // Mix 4 coorners porcentages
  return mix(a, b, u.x) + (c - a)* u.y * (1.0 - u.x) + (d - b) * u.x * u.y;
}



//***********************
//  main function
//***********************
void main(){
  vec2 rp = (gl_FragCoord.xy * 2.0 - resolution) / min(resolution.x, resolution.y);

  // origin rotate
  float s = sin(time);
  float c = cos(time);
  vec2 p = mat2(c, s, -s, c) * rp;

  // camera
  vec3 cPos = vec3(0.0, 0.0, 3.0);
  vec3 cDir = vec3(0.0, 0.0, -1.0);
  vec3 cUp = vec3(0.0, 1.0, 0.0);
  vec3 cSide = cross(cDir, cUp);
  float targetDepth = 1.0;

  // ray defined
  vec3 ray = normalize(cSide * p.x + cUp * p.y + cDir * targetDepth);

  // raymarching
  float dist = 0.0; // min dist
  float rLen = 0.0; // add length
  vec3 rPos = cPos; // ray postion
  for(int i = 0; i < 32; ++i) {
    dist = cube(rPos);
    rLen += dist;
    rPos = cPos + ray * rLen;
  }

  if(abs(dist) < 0.001) {
    vec3 normal = genNormal(rPos);
    vec3 light = normalize(vec3(1.0));
    float diff = max(dot(normal, light), 0.1);
    
    float gradientX = p.x * s + 0.1;
  	float gradientY = p.y * c + 0.1;
    
    float rootColor = gradientX + gradientY + diff * abs(sin(time)) * 2.0 + 0.1;
    gl_FragColor = vec4(vec3(rootColor * baseColor + noise(p)), 10.0);
  } else {
    gl_FragColor = vec4(vec3(noise(p) * compleColor), 1.0);
  }

}

|||

---


#### 000

@@@
{
    "title": "初シェーダー",
    "author": "n_yositaka",
    "description": "初めて書いてみました"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D buckbuffer; // previous scene texture

const float PI = 3.141592;
const float PI2 = PI * 2.0;

void main(){
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / min(resolution.x, resolution.y);
    
    float sp = sin(time * 2.0) * 0.8;
    float cp = cos(time * 2.0) * 0.8;
    
    float maru = 0.3 / sin(length(p));
    
    float a = (atan(p.y, p.x) + PI) / PI2;
    float s = sin(a * PI * 150.0);
    float f = sin(length((p + vec2(sp, cp)) * 50.0) + s - time * 10.0);
    f = (f + 1.0) / 2.0 + 0.1;
    
    float r = sin(length((p + vec2(sp, cp)) * 50.0) + s - (time - 1.0) * 10.0);
    float g = sin(length((p + vec2(sp, cp)) * 50.0) + s - (time - 2.0) * 10.0);
    float b = sin(length((p + vec2(sp, cp)) * 50.0) + s - (time - 3.0) * 10.0);
    vec3 rgb = vec3(r, g, b);

    gl_FragColor = vec4((f + rgb) * maru, 1.0);
}

|||

---


#### 000

@@@
{
    "title": "0011",
    "author": "Aqualamp",
    "description": "0"
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
    vec2 p = (gl_FragCoord.x * 2.0- resolution) *sin(time*22.0);
    vec2 q = (gl_FragCoord.y * 2.0 - resolution) *cos(time*22.0);
    float f = distance(p,q);
    vec2 m = mouse;
        gl_FragColor = vec4(vec2(q),vec2(p)*f);
}

|||

---


#### 000

@@@
{
    "title": "ブラッディ",
    "author": "baco16g",
    "description": "血に染まってる"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)

//***********************
//  lib関数
//***********************
// 2D Random
float random (in vec2 st) {
  return fract(sin(dot(st.xy, vec2(12.9898,78.233))) * 43758.5453123);
}

// 2D Noise based on Morgan McGuire @morgan3d
// https://www.shadertoy.com/view/4dS3Wd
float noise (in vec2 st) {
  vec2 i = floor(st);
  vec2 f = fract(st);

  // Four corners in 2D of a tile
  float a = random(i);
  float b = random(i + vec2(1.0, 0.0));
  float c = random(i + vec2(0.0, 1.0));
  float d = random(i + vec2(1.0, 1.0));

  // Smooth Interpolation

  // Cubic Hermine Curve.  Same as SmoothStep()
  vec2 u = f*f*(3.0-2.0*f);
  // u = smoothstep(0.,1.,f);

  // Mix 4 coorners porcentages
  return mix(a, b, u.x) + (c - a)* u.y * (1.0 - u.x) + (d - b) * u.x * u.y;
}

//***********************
//  main関数
//***********************
void main(){
  // resolutinの正規化処理
  vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / min(resolution.x, resolution.y);

  vec3 baseColor = vec3(0.8, 0.1, 0.1);

  vec2 pos = vec2(p * 200.0) * noise(p * 2.0);
  float n = noise(pos);

  float gradientX = p.x * sin(time);
  float gradientY = p.y * cos(time);

  float rootColor = gradientX + gradientY + n;
  vec3 color = vec3(rootColor * baseColor);
  gl_FragColor = vec4(color, 1.0);
}

|||

---


#### 000

@@@
{
    "title": "test",
    "author": "taquji",
    "description": "backbufferなんか使ってみたかったけど"
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
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / resolution;
    vec2 m = mouse * 2.0 - 1.0;

    float e = 0.15 / length(p - m);
    float f1 = (sin((p.x + time * 0.2) * 40.0) + 1.0) * 0.5 * 0.4;
    float f2 = (sin((p.x + time * 0.4) * 40.0) + 1.0) * 0.5 * 0.5;
    float f3 = (sin((p.x - time * 0.8) * 40.0) + 1.0) * 0.5 * 0.3;

    vec4 b = texture2D(backbuffer, gl_FragCoord.xy / resolution);
    vec4 c = b * vec4(0.2);

    gl_FragColor = vec4(vec3(f1, f2, f3), 1.0) + e + c;
}

|||

---


#### 000

@@@
{
    "title": "hog2",
    "author": "gam0022",
    "description": "hoge（適当）の改良版です"
}
@@@

---

|||
precision highp float;

#extension GL_OES_standard_derivatives : enable

uniform float time;
uniform vec2 mouse;
uniform vec2 resolution;

// consts
const float EPS = 1e-4;
const float OFFSET = EPS * 10.0;
const float PI = 3.14159;
const float INF = 1e+10;

const vec3 lightDir = vec3( -0.48666426339228763, 0.8111071056538127, -0.3244428422615251 );
const vec3 backgroundColor = vec3( 1.0 );
const vec3 gateColor = vec3( 1.0, 1.0, 1.0 );

const float totalTime = 75.0;

// globals
vec3 cPos, cDir;
float normalizedGlobalTime = 0.0;
//vec3 illuminationColor;

struct Intersect {
    bool isHit;

    vec3 position;
    float distance;
    vec3 normal;

    int material;
    vec3 color;
};
    
const int BASIC_MATERIAL = 0;
const int MIRROR_MATERIAL = 1;
const int RAINBOW_MATERIAL = 2;



// distance functions
vec3 opRep( vec3 p, float interval ) {
    return mod( p, interval ) - 0.5 * interval;
}

vec2 opRep( vec2 p, float interval ) {
    return mod( p, interval ) - 0.5 * interval;
}

float opRep( float x, float interval ) {
    return mod( x, interval ) - 0.5 * interval;
}

float sphereDist( vec3 p, vec3 c, float r ) {
    return length( p - c ) - r;
}

float sdCappedCylinder( vec3 p, vec2 h ) {
    vec2 d = abs(vec2(length(p.xz),p.y)) - h;
    return min(max(d.x,d.y),0.0) + length(max(d,0.0));
}

float udBox( vec3 p, vec3 b )
{
    return length(max(abs(p)-b,0.0));
}

float udFloor( vec3 p ){
    float t1 = 1.0;
    float t2 = 3.0;
    float d = 0.0;
    return dot(p,vec3(0.0,1.0,0.0)) - d;
}

float dGate( vec3 p ) {
    p.y -= 1.3 * 0.5;
    
    float r = 0.05;
    float left  = sdCappedCylinder( p - vec3( -1.0, 0.0, 0.0 ),  vec2(r, 1.3));
    float right = sdCappedCylinder( p - vec3( 1.0,  0.0, 0.0 ),  vec2(r, 1.3));

    float ty = 0.02 * p.x * p.x;
    float tx = 0.5 * ( p.y - 1.3 );
    float katsura  = udBox( p - vec3( 0.0, 1.3 + ty, 0.0 ), vec3( 1.7 + tx, r * 2.0 + ty, r ) );

    float kan = udBox( p - vec3( 0.0, 0.7, 0.0 ), vec3( 1.3, r, r ) );
    float gakuduka = udBox( p - vec3( 0.0, 1.0, 0.0), vec3( r, 0.3, r ) );

    return min( min( left, right ), min( gakuduka, min( katsura, kan ) ) );
}

float dRepGate( vec3 p ) {
    if ( normalizedGlobalTime <= 0.5 ) {
        p.z = opRep( p.z, 1.0 + 20.0 * cos( PI * normalizedGlobalTime ) );
    } else {
        p.xz = opRep( p.xz, 10.0  );
    }
    return dGate( p );
}

float gridParam( vec2 p, float interval ) {
    float a = p.x + p.y + 0.5  * interval;
    return floor( a / interval );
}

float dRepCappedCylinder( vec3 p ) {
    float interval = 5.0;
    float tall = cos( gridParam( p.xz , interval ) + time );
    p.xz = opRep( p.xz, interval );
    return sdCappedCylinder( p , vec2( 0.5, 3.0 + tall ) );
}

float sceneDistance( vec3 p ) {
    return min(
        udFloor( p ),
        dRepCappedCylinder( p )
    );
}

// color functions
vec3 hsv2rgb( vec3 c ) {

    vec4 K = vec4( 1.0, 2.0 / 3.0, 1.0 / 3.0, 3.0 );
    vec3 p = abs( fract( c.xxx + K.xyz ) * 6.0 - K.www );
    return c.z * mix( K.xxx, clamp( p - K.xxx, 0.0, 1.0 ), c.y );

}

Intersect minIntersect( Intersect a, Intersect b ) {
    if ( a.distance < b.distance ) {
        return a;
    } else {
        return b;
    }
}

Intersect sceneIntersect( vec3 p ) {

    Intersect a, b;
    a.distance = udFloor( p );
    a.material = BASIC_MATERIAL;
    
    b.distance = dRepCappedCylinder( p );
    b.material = RAINBOW_MATERIAL;
    return minIntersect( a, b );
    //return a;
}

vec3 calcNormal( vec3 p ) {
    vec2 e = vec2( 1.0, -1.0 ) * 0.001;
    return normalize(
        e.xyy * sceneDistance( p + e.xyy ) + e.yyx * sceneDistance( p + e.yyx ) + 
        e.yxy * sceneDistance( p + e.yxy ) + e.xxx * sceneDistance( p + e.xxx ) );
}

float calcShadow( vec3 ro, vec3 rd ) {

    float h = 0.0;
    float c = 0.0;
    float r = 1.0;
    float shadowCoef = 0.5;

    for ( float t = 0.0; t < 50.0; t++ ) {

        h = sceneDistance( ro + rd * c );

        if ( h < EPS ) return shadowCoef;

        r = min( r, h * 16.0 / c );
        c += h;

    }

    return 1.0 - shadowCoef + r * shadowCoef;

}


float calcAO(vec3 pos, vec3 normal) {
    float k = 1.0, occluded = 0.0;
    for (int i = 0; i < 5; i++) {
        float length = 1.5 * float(i);
        float distance = sceneDistance(normal * length + pos);
        occluded += (length - distance) * k;
        k *= 0.1;
    }
    return clamp(1.0 - occluded, 0.0, 1.0);
}

Intersect getRayColor( vec3 origin, vec3 ray ) {

    // marching loop
    float d, minDist, trueDepth;
    float distance = 0.0;
    vec3 p = origin;
    int count = 0;
    Intersect nearest;

    // first pass (water)
    for ( int i = 0; i < 120; i++ ){

        d = sceneDistance( p );
        distance += d;
        p = origin + distance * ray;

        count = i;
        if ( abs(d) < EPS ) break;

    }

    if ( abs(d) < EPS ) {

        nearest = sceneIntersect( p );
        nearest.position = p;
        nearest.normal = calcNormal(p);
        nearest.distance = distance;
        float diffuse = clamp( dot( lightDir, nearest.normal ), 0.0, 1.0 );
        float specular = pow( clamp( dot( reflect( lightDir, nearest.normal ), ray ), 0.0, 1.0 ), 6.0 );
        float shadow = calcShadow( p + nearest.normal * OFFSET, lightDir );
    float ao = calcAO( p, nearest.normal );  

        if ( nearest.material == BASIC_MATERIAL ) {
        nearest.color = vec3( 1.0 ) * diffuse * ao * shadow;
        } else if ( nearest.material == RAINBOW_MATERIAL ) {
            nearest.color = hsv2rgb( vec3( gridParam( p.xz , 5.0 ) * 0.1, 1.0, 1.0 ) ) * diffuse + vec3( 1.0 ) * specular;
        } else if ( nearest.material == MIRROR_MATERIAL ) {
            nearest.color = vec3( 0.7 ) * diffuse + vec3( 1.0 ) * specular;
        }

        nearest.isHit = true;

    } else {

        nearest.color = backgroundColor;
        nearest.isHit = false;

    }
    nearest.color = clamp( nearest.color + 0.01 * nearest.distance, 0.0, 1.0 );

    // second pass (gates)
    /*p = origin;
    distance = 0.0;
    minDist = INF;
    for ( int i = 0; i < 20; i++ ){
        d = dRepGate( p );
        minDist = min(d, minDist);
        //if ( d < minDist ) {
        //    minDist = d;
        //    trueDepth = distance;
        //}
        distance += d;
        p = origin + distance * ray;
        if ( i == 9 && normalizedGlobalTime <= 0.5 ) {
            break;
        }
    }

    if ( abs(d) < EPS ) {
        nearest.color += gateColor;
    } else {
        nearest.color += gateColor * clamp( 0.05 / minDist, 0.0, 1.0 );
    }*/

    return nearest;

}

void main( void ) {
    normalizedGlobalTime = mod( time / totalTime, 1.0 );

    // fragment position
    vec2 p = ( gl_FragCoord.xy * 2.0 - resolution.xy ) / min(  resolution.x,  resolution.y );

    // camera and ray
    //if ( normalizedGlobalTime < 0.7 ) {
    //    cPos = vec3( 0.0, 0.8 + 0.4 * cos( time ), 3.0 * time );
    //    cDir = normalize( vec3( 0.0, -0.1, 1.0 ) );
    //} else {
        cPos = vec3( 0.0, 6.2, 3.0 * time );
        cDir = normalize( vec3( 0.0, -0.3, 1.0 ) );
    //}
    vec3 cSide = normalize( cross( cDir, vec3( 0.0, 1.0 ,0.0 ) ) );
    vec3 cUp   = normalize( cross( cSide, cDir ) );
    float targetDepth = 1.3;
    vec3 ray = normalize( cSide * p.x + cUp * p.y + cDir * targetDepth );

    // Illumination Color
    // illuminationColor = hsv2rgb( vec3( time * 0.02 + 0.6, 1.0, 1.0 ) );

    vec3 color = vec3( 0.0 );
    float alpha = 1.0;
    Intersect nearest;

    for ( int i = 0; i < 3; i++ ) {

        nearest = getRayColor( cPos, ray );

        color += alpha * nearest.color;
        alpha *= 0.5;
        ray = normalize( reflect( ray, nearest.normal ) );
        cPos = nearest.position + nearest.normal * OFFSET;

        if ( !nearest.isHit || nearest.material != MIRROR_MATERIAL ) break;

    }

    gl_FragColor  = vec4(color, 1.0);

}
|||

---


#### 000

@@@
{
    "title": "ジャズと共に",
    "author": "hgoe",
    "description": "上下にアニメーションさせたり、\nマウスxyから、線を縦横に分けたりしたかったやつ"
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
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / resolution;
    vec2 q = mod(p, 0.2) - 0.1;
    float t = fract(time / 2.0);
    
    float v = 0.02 / length(q.y) + t;
    v -= 0.5;
 
    gl_FragColor = vec4(vec3(v), 1.0);
}

|||

---


#### 000

@@@
{
    "title": "Sushi Stream",
    "author": "notargs",
    "description": "滑り込みセーフ！！"
}
@@@

---

|||
#ifdef GL_ES
precision mediump float;
#endif

#extension GL_OES_standard_derivatives : enable

uniform float time;
uniform vec2 mouse;
uniform vec2 resolution;

mat3 rotY(float a)
{
    return mat3(cos(a), 0, -sin(a),
           0, 1, 0,
           sin(a), 0, cos(a));
}
mat3 rotZ(float a)
{
    return mat3(cos(a), -sin(a), 0,
           sin(a), cos(a), 0,
           0, 0, 1);
}
// 球を定義
float sphere(vec3 p)
{
    return length(p) - 1.0;
}

float udRoundBox( vec3 p, vec3 b, float r )
{
    return length(max(abs(p)-b,0.0)) - r;
}


vec3 transformSushiSpace(vec3 p)
{
    mat3 rot = rotZ(p.z * 0.02);
    p = rot * p;
    vec3 rp = p;
    p *= rotY(time * 1.0 + length(rp-p)*123.456);
    p = mod(p, 10.0) - 5.0;
    return p;
}

float salmon(vec3 p)
{
    p = transformSushiSpace(p);
    return udRoundBox(p + vec3(0, -0.35 - cos(p.x / 3.0), 0), vec3(3.0, 0.04, 1.0), 0.2);
}


float shari(vec3 p)
{
    p = transformSushiSpace(p);
    return udRoundBox(p, vec3(1.5, 0.3, 0.3), 1.0);
}


vec3 getColor(vec3 p)
{
    if (salmon(p) < 0.1)
    {	
        p = transformSushiSpace(p);
        return mix(vec3(1, 0.3, 0), vec3(1, 1, 1), clamp(sin(p.x * 5.0 + abs(p.z)) - 0.5, 0.0, 1.0));
    }
    
    return vec3(1, 1, 1);
}


// 距離感数
float dist(vec3 p)
{
    return min(salmon(p), shari(p));
}

vec3 getNormal(vec3 p)
{
    float ep = 0.001;
    return normalize(vec3(dist(p) - dist(p - vec3(ep, 0, 0)),
                 dist(p) - dist(p - vec3(0, ep, 0)),
                 dist(p) - dist(p - vec3(0, 0, ep))));
}

void main( void ) {

    vec2 tex = (gl_FragCoord.xy - resolution.xy / 2.0) / resolution.y;
    
    mat3 rot = rotZ(time / 0.8 + sin(time * 2.0));
    
    vec3 pos = rot * vec3(0, 0, time * 0.0);
    vec3 dir = rot * normalize(vec3(tex, 0.8));
    
    vec3 color = vec3(0.0, 0.0, 0.0);
    
    // レイマーチング
    for(float i = 0.0; i < 32.0; i++)
    {
        float d = dist(pos);
        if (d < 0.1)
        {
            color = (max(dot(vec3(1, 1, -1), getNormal(pos)), 0.0) + 0.2) * getColor(pos);
            break;
        }
        
        pos += dir * d;
    }
    
    gl_FragColor = vec4(color, 1.0 );

}
|||

---


#### 000

@@@
{
    "title": "zawazawa",
    "author": "zawa",
    "description": "zawawa"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

const float PI = 3.14;
const float PI2 = PI * 2.0;

void main(){
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / resolution;
    
    float g = sin(time * 2.0) * sin(p.x * 10.0) + sin(p.y * 50.0);
    
    gl_FragColor = vec4(vec3(g, g, g), 0.8);
}

|||

---


#### 000

@@@
{
    "title": "musasabi",
    "author": "musasabi",
    "description": "musasabi"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

const float PI = 3.1415926;

void main(){
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / resolution; // -1.0 ~ 1.0
    
    mat2 r2 = mat2(
        cos(time), -sin(time),
        sin(time), cos(time)
    );
    
    p = r2 * p * vec2(1.6);
    
    float t = sin(time) * cos(time * 2.0);
    mat2 r = mat2(
        cos(t), -sin(t),
        sin(t), cos(t)
    );
    float scale = 30.0 + sin(time) * 5.0;
    vec2 ps = vec2(sin(p * scale));
    vec2 pc = vec2(cos(p * scale));
    float l = length(p * 1.5);
    
    gl_FragColor = vec4(1.0, r * (ps + pc) - l, .6);
}
|||

---


#### 000

@@@
{
    "title": "no-title",
    "author": "yuichiroharai",
    "description": "長谷川さんの講義の\n一方は0-1、一方は1-0のヤツ（？）を参考に\n縦と横のノイズ模様を切り替えたもの。\nかつ、なんとなくランダムになるようにして、どっちが出るのか分からないみたいにしてみました。"
}
@@@

---

|||
precision highp float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

const float PI = 3.141592653589793;
const float PI_2 = 6.283185307179586;

//
// Description : Array and textureless GLSL 2D/3D/4D simplex
//               noise functions.
//      Author : Ian McEwan, Ashima Arts.
//  Maintainer : ijm
//     Lastmod : 20110822 (ijm)
//     License : Copyright (C) 2011 Ashima Arts. All rights reserved.
//               Distributed under the MIT License. See LICENSE file.
//               https://github.com/ashima/webgl-noise
//

vec3 mod289(vec3 x) {
  return x - floor(x * (1.0 / 289.0)) * 289.0;
}

vec4 mod289(vec4 x) {
  return x - floor(x * (1.0 / 289.0)) * 289.0;
}

vec4 permute(vec4 x) {
     return mod289(((x*34.0)+1.0)*x);
}

vec4 taylorInvSqrt(vec4 r)
{
  return 1.79284291400159 - 0.85373472095314 * r;
}

float snoise(vec3 v)
  {
  const vec2  C = vec2(1.0/6.0, 1.0/3.0) ;
  const vec4  D = vec4(0.0, 0.5, 1.0, 2.0);

// First corner
  vec3 i  = floor(v + dot(v, C.yyy) );
  vec3 x0 =   v - i + dot(i, C.xxx) ;

// Other corners
  vec3 g = step(x0.yzx, x0.xyz);
  vec3 l = 1.0 - g;
  vec3 i1 = min( g.xyz, l.zxy );
  vec3 i2 = max( g.xyz, l.zxy );

  //   x0 = x0 - 0.0 + 0.0 * C.xxx;
  //   x1 = x0 - i1  + 1.0 * C.xxx;
  //   x2 = x0 - i2  + 2.0 * C.xxx;
  //   x3 = x0 - 1.0 + 3.0 * C.xxx;
  vec3 x1 = x0 - i1 + C.xxx;
  vec3 x2 = x0 - i2 + C.yyy; // 2.0*C.x = 1/3 = C.y
  vec3 x3 = x0 - D.yyy;      // -1.0+3.0*C.x = -0.5 = -D.y

// Permutations
  i = mod289(i);
  vec4 p = permute( permute( permute(
             i.z + vec4(0.0, i1.z, i2.z, 1.0 ))
           + i.y + vec4(0.0, i1.y, i2.y, 1.0 ))
           + i.x + vec4(0.0, i1.x, i2.x, 1.0 ));

// Gradients: 7x7 points over a square, mapped onto an octahedron.
// The ring size 17*17 = 289 is close to a multiple of 49 (49*6 = 294)
  float n_ = 0.142857142857; // 1.0/7.0
  vec3  ns = n_ * D.wyz - D.xzx;

  vec4 j = p - 49.0 * floor(p * ns.z * ns.z);  //  mod(p,7*7)

  vec4 x_ = floor(j * ns.z);
  vec4 y_ = floor(j - 7.0 * x_ );    // mod(j,N)

  vec4 x = x_ *ns.x + ns.yyyy;
  vec4 y = y_ *ns.x + ns.yyyy;
  vec4 h = 1.0 - abs(x) - abs(y);

  vec4 b0 = vec4( x.xy, y.xy );
  vec4 b1 = vec4( x.zw, y.zw );

  //vec4 s0 = vec4(lessThan(b0,0.0))*2.0 - 1.0;
  //vec4 s1 = vec4(lessThan(b1,0.0))*2.0 - 1.0;
  vec4 s0 = floor(b0)*2.0 + 1.0;
  vec4 s1 = floor(b1)*2.0 + 1.0;
  vec4 sh = -step(h, vec4(0.0));

  vec4 a0 = b0.xzyw + s0.xzyw*sh.xxyy ;
  vec4 a1 = b1.xzyw + s1.xzyw*sh.zzww ;

  vec3 p0 = vec3(a0.xy,h.x);
  vec3 p1 = vec3(a0.zw,h.y);
  vec3 p2 = vec3(a1.xy,h.z);
  vec3 p3 = vec3(a1.zw,h.w);

//Normalise gradients
  vec4 norm = taylorInvSqrt(vec4(dot(p0,p0), dot(p1,p1), dot(p2, p2), dot(p3,p3)));
  p0 *= norm.x;
  p1 *= norm.y;
  p2 *= norm.z;
  p3 *= norm.w;

// Mix final noise value
  vec4 m = max(0.6 - vec4(dot(x0,x0), dot(x1,x1), dot(x2,x2), dot(x3,x3)), 0.0);
  m = m * m;
  return 42.0 * dot( m*m, vec4( dot(p0,x0), dot(p1,x1),
                                dot(p2,x2), dot(p3,x3) ) );
  }

float ease(float t) {
  return t == 0.0 || t == 1.0
    ? t
    : t < 0.5
      ? +0.5 * pow(2.0, (20.0 * t) - 10.0)
      : -0.5 * pow(2.0, 10.0 - (t * 20.0)) + 1.0;
}
float zeroOne(float x) {
    return x * 0.5 + 0.5;
}

void main(){
    vec2 uv = gl_FragCoord.xy / resolution - 0.5;

    float t1 = ease(zeroOne(sin(time / 7.0 * PI_2)));
    float t2 = ease(zeroOne(sin(time / 5.0 * PI_2)));
    float t3 = ease(zeroOne(sin(time / 3.0 * PI_2)));
    float u1 = 1.0 - t1;
    float u2 = 1.0 - t2;
    float u3 = 1.0 - t3;
    vec2 p = vec2(32.0 * t1 * t2 * t3, 32.0 * u1 * u2 * u3);

    float r = zeroOne(snoise(vec3(uv * p, time)));
    vec3 rgb = vec3(r);

    gl_FragColor = vec4(rgb, 1.0);
}

|||

---


#### 000

@@@
{
    "title": "ステンドグラスっぽい何か",
    "author": "shuto",
    "description": "初めてのglsl（修正版）"
}
@@@

---

|||
precision mediump float;
uniform vec2  resolution;     // resolution (width, height)
uniform vec2  mouse;          // mouse      (0.0 ~ 1.0)
uniform float time;           // time       (1second == 1.0)
uniform sampler2D backbuffer; // previous scene texture

const float PI = 3.1415926;
const float PI2 = PI * 2.0;


void main(){
    vec2 p = (gl_FragCoord.xy * 2.0 - resolution) / resolution.x;
    float a = (atan(p.y, p.x) + PI) / PI2;
    float a2 = (atan(time*PI2, time*PI) + PI) / PI2;
    float s = sin(a * PI * 40.0);
    float x = length( p*50.0 ) - time* 20.0;
    float f = sin(x)/PI*x*0.5;
    float f1 = sin(length(a* 60.0) + s + time * 0.0);
    float f2 = sin(length(p* 40.0) + s - time * 10.0) - f1;
    float f3 = sin(length(p* 30.0) + s - time * 10.0) + f2;
    float m = 0.1 / length(p - vec2(cos(time*8.0)*0.3, sin(time*5.0)));
    m += 0.1 / length(p - vec2(cos(time*7.0)*0.6, 0.5*sin(time*9.0)));;
    m += 0.1 / length(p - vec2(cos(time*2.0)*0.3, 0.2*sin(time*3.0)));
    gl_FragColor = vec4(vec3(f1, f2, f3)*m*f*a2, 1.0);
    
}
|||

---


---

## enjoy shader life

---

## enjoy shader life

### thank you!!

---


