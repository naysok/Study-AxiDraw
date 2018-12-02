# Study-AxiDraw  

axidraw  
[https://axidraw.com/](https://axidraw.com/)  
[https://github.com/evil-mad/axidraw](https://github.com/evil-mad/axidraw)  


---  


### うまくいかないらしい（181127）  

実際の様子がわからないけど、SVG ファイルが原因？  
再起動、win/mac はテスト済みらしい。  

うまくいくらしい example SVG を、atom で開いて確認。  
メタデータに inkScape で書き出されているとか書いてる  
SVG のバージョンは 1.1  
[https://github.com/evil-mad/axidraw/tree/master/examples](https://github.com/evil-mad/axidraw/tree/master/examples)  


うまくいかないらしい illustrator 製 SVG も、SVG のバージョンは同じ  


少しテキストで確認すると、パスの記述方法が違う。  
examples の inkScape の方は、どのファイル、どんなパスも、 <path > で、制御点で記述されている。  
illustrator の方は、  
四角は <rect > で基準の点+大きさ、円は <circle >で基準点+大きさみたいな、値を記述されている。  

inkScape ではこの記述は NG？？  
illustrator で　SVG を書き出して、inkScape で読み込みで失敗している？  


inkScape の SVG（examples）  
```xml
<path
   inkscape:connector-curvature="0"
   id="path4829"
   d="m 70.003198,74.244046 a 2.0113185,2.0113185 0 0 0 -0.05071,0.002 2.0113185,2.0113185 0 0 0 -0.141206,0.0051 2.0113185,2.0113185 0 0 0 -0.009,0 2.0113185,2.0113185 0 0 0 -0.0099,10e-4 2.0113185,2.0113185 0 0 0 -1.764106,1.425999 L 56.742603,100.39254 a 2.0113879,2.0113879 0 1 0 3.65947,1.67063 l 2.81421,-6.162429 13.390874,0 2.775429,6.154469 a 2.0113185,2.0113185 0 1 0 3.666435,-1.65372 L 71.907522,75.698084 A 2.0113185,2.0113185 0 0 0 70.110607,74.2512 2.0113185,2.0113185 0 0 0 70.044977,74.2471 2.0113185,2.0113185 0 0 0 70.003227,74.244 Z m -0.05071,6.90327 4.840841,10.731796 -9.741348,0 4.900507,-10.731796 z"
   style="color:#000000;font-style:normal;font-variant:normal;font-weight:normal;font-stretch:normal;font-size:medium;line-height:normal;font-family:sans-serif;text-indent:0;text-align:start;text-decoration:none;text-decoration-line:none;text-decoration-style:solid;text-decoration-color:#000000;letter-spacing:normal;word-spacing:normal;text-transform:none;direction:ltr;block-progression:tb;writing-mode:lr-tb;baseline-shift:baseline;text-anchor:start;white-space:normal;clip-rule:nonzero;display:inline;overflow:visible;visibility:visible;opacity:1;isolation:auto;mix-blend-mode:normal;color-interpolation:sRGB;color-interpolation-filters:linearRGB;solid-color:#000000;solid-opacity:1;fill:none;fill-opacity:1;fill-rule:nonzero;stroke:#000000;stroke-width:0.71644276;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;color-rendering:auto;image-rendering:auto;shape-rendering:auto;text-rendering:auto;enable-background:accumulate" />
<path
   inkscape:connector-curvature="0"
   id="path4831"
   d="m 123.9227,74.244046 a 2.0113185,2.0113185 0 0 0 -1.38722,0.586707 2.0113185,2.0113185 0 0 0 -0.0398,0.0388 2.0113185,2.0113185 0 0 0 -0.0159,0.01792 2.0113185,2.0113185 0 0 0 -0.53798,1.716369 l 0,24.295698 a 2.0113185,2.0113185 0 0 0 0.56284,1.74819 2.0113185,2.0113185 0 0 0 0.0388,0.0398 2.0113185,2.0113185 0 0 0 0.007,0.007 2.0113185,2.0113185 0 0 0 1.72333,0.54197 l 6.30861,0 a 2.0113185,2.0113185 0 0 0 0.002,0 c 3.32305,-0.004 6.88782,-0.89287 9.73738,-3.21795 2.84955,-2.325084 4.81547,-6.107517 4.94724,-11.190222 0.13398,-5.16765 -2.02294,-9.01229 -4.91642,-11.321486 -2.89348,-2.309195 -6.37111,-3.211978 -9.25607,-3.211978 -2.91131,-0.04827 -4.08585,-0.01186 -6.80284,-0.02088 a 2.0113185,2.0113185 0 0 0 -0.37092,-0.02984 z m 2.04155,4.056246 c 1.59947,-0.0046 2.92626,-0.02052 5.0984,0.01588 a 2.0113185,2.0113185 0 0 0 0.0338,0.001 c 1.99542,0 4.71903,0.715122 6.74616,2.332911 2.02712,1.617789 3.51126,4.009348 3.40589,8.073705 -0.10758,4.149311 -1.52072,6.587992 -3.46954,8.178119 -1.94807,1.589521 -4.60017,2.308702 -7.19662,2.312032 l -4.6181,0 0,-20.913671 z"
   style="color:#000000;font-style:normal;font-variant:normal;font-weight:normal;font-stretch:normal;font-size:medium;line-height:normal;font-family:sans-serif;text-indent:0;text-align:start;text-decoration:none;text-decoration-line:none;text-decoration-style:solid;text-decoration-color:#000000;letter-spacing:normal;word-spacing:normal;text-transform:none;direction:ltr;block-progression:tb;writing-mode:lr-tb;baseline-shift:baseline;text-anchor:start;white-space:normal;clip-rule:nonzero;display:inline;overflow:visible;visibility:visible;opacity:1;isolation:auto;mix-blend-mode:normal;color-interpolation:sRGB;color-interpolation-filters:linearRGB;solid-color:#000000;solid-opacity:1;fill:none;fill-opacity:1;fill-rule:nonzero;stroke:#000000;stroke-width:0.71644276;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:4;stroke-dasharray:none;stroke-dashoffset:0;stroke-opacity:1;color-rendering:auto;image-rendering:auto;shape-rendering:auto;text-rendering:auto;enable-background:accumulate" />
```

illustrator の SVG  
```xml
<rect x="162.7" y="765.4" class="st0" width="1.6" height="0.5"/>
<path class="st0" d="M63.3,742h-0.7c0.2,0.7,0.4,1.5,0.6,2.2c0.1-0.4,0.2-0.9,0.3-1.4C63.4,742.6,63.3,742.3,63.3,742z"/>
<path class="st0" d="M148.8,793.2h-2c0,2.3-0.2,4.2-0.6,5.8v0.1c1-0.1,1.9-0.2,2.6-0.4V793.2z"/>
<path class="st0" d="M164.3,798.3v-5h-1.6v5.7C163.6,798.8,164.1,798.6,164.3,798.3z"/>
<rect x="146.2" y="782.8" class="st0" width="2.6" height="0.1"/>
```



---  



### マシンの制御  


作者のアカウントからソースコードを読む  
[https://github.com/evil-mad](https://github.com/evil-mad)  


axidraw のリポジトリ  
inkScape のエクステンションのソースコード  
.inx が、inkScape のスクリプト  
[https://github.com/evil-mad/axidraw](https://github.com/evil-mad/axidraw)  

```python
import ebb_motion  # Requires v 0.15 in plotink     https://github.com/evil-mad/plotink
import ebb_serial  # Requires v 0.11 in plotink
import inkex
import plot_utils  # Requires v 0.10 in plotink
```


なんか、plotink を読み込んでいるのでそっちを確認。  
[https://github.com/evil-mad/plotink](https://github.com/evil-mad/plotink)  



一番下は、多分これ、ebb_serial.py。  
ここで、いくつか接続系、クエリ系の一番低レベルな関数を作っていて、axidraw などでもこれを呼び出してる。  

ここで、
```python
import serial
```
してるので、pySerial で、シリアルを送って制御。  

ポート探し  
```python
def findPort():
    # Find first available EiBotBoard by searching USB ports.
    # Return serial port object.
    try:
        from serial.tools.list_ports import comports
    except ImportError:
        return None
    if comports:
        com_ports_list = list(comports())
        ebb_port = None
        for port in com_ports_list:
            if port[1].startswith("EiBotBoard"):
                ebb_port = port[0]  # Success; EBB found by name match.
                break  # stop searching-- we are done.
        if ebb_port is None:
            for port in com_ports_list:
                if port[2].startswith("USB VID:PID=04D8:FD92"):
                    ebb_port = port[0]  # Success; EBB found by VID/PID match.
                    break  # stop searching-- we are done.
        return ebb_port
```

クエリ処理  
query と command 、複数ある  
```python
def command(port_name, cmd):
    if port_name is not None and cmd is not None:
        try:
            port_name.write(cmd.encode('ascii'))
            response = port_name.readline().decode('ascii')
            n_retry_count = 0
            while len(response) == 0 and n_retry_count < 100:
                # get new response to replace null response if necessary
                response = port_name.readline().decode('ascii')
                n_retry_count += 1
            if response.strip().startswith("OK"):
                # Debug option: indicate which command:
                # inkex.errormsg( 'OK after command: ' + cmd )
                pass
            else:
                if response:
                    inkex.errormsg('Error: Unexpected response from EBB.')
                    inkex.errormsg('   Command: {0}'.format(cmd.strip()))
                    inkex.errormsg('   Response: {0}'.format(response.strip()))
                else:
                    inkex.errormsg('EBB Serial Timeout after command: {0}'.format(cmd))
        except:
            if cmd.strip().lower() not in ["rb"]: # Ignore error on reboot (RB) command
	            inkex.errormsg('Failed after command: {0}'.format(cmd))

```

[https://github.com/evil-mad/plotink/blob/master/libraries/ebb_serial.py](https://github.com/evil-mad/plotink/blob/master/libraries/ebb_serial.py)  



その上で、ebb_motion.py で、基本的な2点間移動などの関数を作っている  

ebb_serial.py の読み込み  
```python
import ebb_serial
```

2点間移動  
str_output で整形して、command に送っている  
```python
def doABMove(port_name, delta_a, delta_b, duration):
    # Issue command to move A/B axes as: "XM,<move_duration>,<axisA>,<axisB><CR>"
    # Then, <Axis1> moves by <AxisA> + <AxisB>, and <Axis2> as <AxisA> - <AxisB>
    if port_name is not None:
        str_output = 'XM,{0},{1},{2}\r'.format(duration, delta_a, delta_b)
        ebb_serial.command(port_name, str_output)

```

ペンの上下  
2つ目の引数は、axidraw の方では、ハードコーディングされていると思う。
```python
def setPenDownRate(port_name, pen_down_rate):
    if port_name is not None:
        ebb_serial.command(port_name, 'SC,12,{0}\r'.format(pen_down_rate))
        # Set the rate of change of the servo when going down.
        # http://evil-mad.github.io/EggBot/ebb.html#SC

def setPenUpPos(port_name, servo_min):
    if port_name is not None:
        ebb_serial.command(port_name, 'SC,4,{0}\r'.format(servo_min))
        # servo_min may be in the range 1 to 65535, in units of 83 ns intervals. This sets the "Pen Up" position.
        # http://evil-mad.github.io/EggBot/ebb.html#SC

```

ペンの状態を問い合わせる  
```python
def TogglePen(port_name):
    if port_name is not None:
        ebb_serial.command(port_name, 'TP\r')

```

[https://github.com/evil-mad/plotink/blob/master/libraries/ebb_motion.py](https://github.com/evil-mad/plotink/blob/master/libraries/ebb_motion.py)  


整形され、 command で送られる文字列はこんな感じ  
```xml
SC,4,{0}\r <!-- {0} はフォーマット -->
TP\r
```

これらを、axidraw のハードウェア側にのったファームウェアで解釈してるはず。  
ファームウェアを読めれば、pySerial を使って、フルスクラッチで作り込めるっぽいので良さそう。  
ファームウェアはどれ...  



---  

