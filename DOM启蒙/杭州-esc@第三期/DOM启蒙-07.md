# ��Dom���ɡ�����ʼ�


## ��10�� DOM�е�javaScript

 
function loadJs(id,url,callback){  
    var script = document.createElement('script');  
    script.type = 'text/javascript';  
    script.src = url;  
    script.id = id;  
    script.onload = script.onreadystatechange = function(){  
        alert(script.readyState);  
        if(script.readyState  && script.readyState != 'loaded' && script.readyState != 'complete') return ;  
        script.onreadystatechange = script.onload = null  
        if(callback) callback();  
    }  
    document.body.appendChild(script);       
}  


##ʹ��async�첽���ز�ִ���ⲿjs�ļ�

 һ��ͬ������
����ƽʱʹ�õ�����һ�ַ�ʽ��
<script src="http://yourdomain.com/script.js"></script>
<script src="http://yourdomain.com/script.js"></script>
ͬ��ģʽ���ֳ�����ģʽ������ֹ������ĺ�������ֹͣ�����Ľ�����ֻ�е���ǰ������ɣ����ܽ�����һ������������Ĭ��ͬ��ִ�в��ǰ�ȫ�ġ����������js�������document���ݡ��޸�dom���ض������Ϊ���ͻ����ҳ�����������һ�㽨���<script>��ǩ����<body>��β�������������ܼ���ҳ��������
�����첽����
�첽�����ֽз��������أ������������ִ��js��ͬʱ������������к���ҳ��Ĵ�����Ҫ�����ַ�ʽ��
����һ��Ҳ��Script DOM Element
(function(){
    var scriptEle = document.createElement("script");
    scriptEle.type = "text/javasctipt";
    scriptEle.async = true;
    scriptEle.src = "http://cdn.bootcss.com/jquery/3.0.0-beta1/jquery.min.js";
    var x = document.getElementsByTagName("head")[0];
    x.insertBefore(scriptEle, x.firstChild);		
 })();
<async>������HTML5���������첽֧�֡��˷�������ΪScript DOM Element ������Google Analytics �� Google+ Badge ��ʹ���������첽���ش���
(function(){;
    var ga = document.createElement('script'); 
    ga.type = 'text/javascript'; 
    ga.async = true; 
    ga.src = ('https:' == document.location.protocol ? 'https://ssl' : 'http://www') + '.google-analytics.com/ga.js'; 
    var s = document.getElementsByTagName('script')[0]; 
    s.parentNode.insertBefore(ga, s); 
})();
�������ּ��ط�ʽִ����֮ǰ����ֹonload�¼��Ĵ����������ںܶ�ҳ��Ĵ��붼��onloadʱ��ִ�ж������Ⱦ���������Ի��ǻ���������ҳ��ĳ�ʼ������
��������onloadʱ���첽����
(function(){
	if(window.attachEvent){
    	window.attachEvent("load", asyncLoad);
    }else{
    	window.addEventListener("load", asyncLoad);
    }
    var asyncLoad = function(){
    	var ga = document.createElement('script'); 
        ga.type = 'text/javascript'; 
        ga.async = true; 
        ga.src = ('https:' == document.location.protocol ? 'https://ssl' : 'http://www') + '.google-analytics.com/ga.js'; 
        var s = document.getElementsByTagName('script')[0]; 
        s.parentNode.insertBefore(ga, s);
    }
)();
���ַ���ֻ�ǰѲ���script�ķ�������һ���������棬Ȼ�����window��onload��������ִ�У������ͽ��������onload�¼����������⡣
ע:DOMContentLoaded��load������ǰ������document�Ѿ�������ɣ�ҳ���е�domԪ�ؿ��ã�����ҳ���е�ͼƬ����Ƶ����Ƶ����Դδ�����꣬����ͬjQuery�е�ready�¼������ߵ���������ҳ��������Դȫ��������ϡ�
����������������
����JavaScript�Ķ�̬�ԣ����кܶ��첽���ط����� XHR Injection�� XHR Eval�� Script In Iframe�� Script defer���ԡ� document.write(script tag)��
XHR Injection(XHR ע��)��ͨ��XMLHttpRequest����ȡjavascript��Ȼ�󴴽�һ��scriptԪ�ز��뵽DOM�ṹ�С�ajax����ɹ�������script.textΪ����ɹ��󷵻ص�responseText��
    //��ȡXMLHttpRequest���󣬿��Ǽ����ԡ�
    var getXmlHttp = function(){
        var obj;
        if (window.XMLHttpRequest)
            obj = new XMLHttpRequest();
        else
            obj = new ActiveXObject("Microsoft.XMLHTTP");
        return obj;
    };  
    //����Http����get��ʽ;open()�����ĵ�����������ʾ�����첽(true)����ͬ��(false)����
    var xmlHttp = getXmlHttp();
    xmlHttp.open("GET", "http://cdn.bootcss.com/jquery/3.0.0-beta1/jquery.min.js", true);
    xmlHttp.send(); 
    xmlHttp.onreadystatechange = function(){
        if (xmlHttp.readyState == 4 && xmlHttp.status == 200){
            var script = document.createElement("script");
            script.text = xmlHttp.responseText;
            document.getElementsByTagName("head")[0].appendChild(script);
        }
    }		
XHR Eval����XHR Injection��responseText��ִ�з�ʽ��ͬ��ֱ�Ӱ�responseText����eval()��������ִ�С�
    //��ȡXMLHttpRequest���󣬿��Ǽ����ԡ�
    var getXmlHttp = function(){
        var obj;
        if (window.XMLHttpRequest)
            obj = new XMLHttpRequest();
        else
            obj = new ActiveXObject("Microsoft.XMLHTTP");
        return obj;
    };  
    //����Http����get��ʽ;open()�����ĵ�����������ʾ�����첽(true)����ͬ��(false)����
    var xmlHttp = getXmlHttp();
    xmlHttp.open("GET", "http://cdn.bootcss.com/jquery/3.0.0-beta1/jquery.min.js", true);
    xmlHttp.send(); 
    xmlHttp.onreadystatechange = function(){
        if (xmlHttp.readyState == 4 && xmlHttp.status == 200){
            eval(xmlHttp.responseText);
            //alert($);//���Ե���$,����JS�Ѿ����ؽ�����click�¼�����������������⣬Ӧ���ǻ�û���ؽ���
            $("#btn1").click(function(){
                alert($(this).text());
            });
        }
    }		
Script In Irame���ڸ����ڲ���һ��iframeԪ�أ�Ȼ����iframe��ִ�м���JS�Ĳ�����
    var insertJS = function(){alert(2)};
    var iframe = document.createElement("iframe");
    document.body.appendChild(iframe);
    var doc = iframe.contentWindow.document;//��ȡiframe�е�windowҪ��contentWindow���ԡ�
    doc.open();
    doc.write("<script>var insertJS = function(){};<\/script><body onload='insertJS()'></body>");
    doc.close();
GMail Mobile��ҵ��JS���ݱ�ע�ͣ����Բ���ִ�У�����Ҫ��ʱ�򣬻�ȡscript�е�text����ȥ��ע�ͣ�����eval()ִ�С�
    <script type="text/javascript"> 
    /* 
    var ... 
    */ 
    </script>
HTML5�����ԣ�async��defer����
defer���ԣ�IE4.0�ͳ��֡�defer�������ű��н�������document.write��dom�޸ġ�������Ტ������������defer���Ե�script������������ҳ���������ע�����е�defer�ű����뱣֤��˳��ִ�еġ�
    <script type="text/javascript" defer></script>
async���ԣ�Html5�����ԡ��ű��������غ󾡿�ִ�У�����ͬdefer�����ǲ��ܱ�֤�ű���˳��ִ�С����ǽ���onload�¼�֮ǰ��ɡ�
    <script type="text/javascript" defer></script>
Firefox 3.6��Opera 10.5��IE 9�����µ�Chrome��Safari��֧��async���ԡ�����ͬʱʹ��async��defer������IE 4֮�������IE��֧���첽���ء�
û��async���ԣ�script��������ȡ�����أ���ִ�У��ڼ�������������ĺ������������async���ԣ���ôscript�����첽���ز�ִ�У�ͬʱ��������������Ĵ���
�ܽ᣺ ����֧��HTML5���������ʵ��JS���첽����ֻ��Ҫ��scriptԪ���м���async���ԣ�Ϊ�˼����ϰ汾��IE�������defer���ԣ����ڲ�֧��HTML5�������(IE������deferʵ��)�����Բ������ϼ��ַ���ʵ�֡�ԭ������϶�����DOM��д��script����ͨ��eval����ִ��JS���룬����԰�����������������ִ�У�Ҳ������onload��ִ�У�Ҳ����ͨ��XHRע��ʵ�֣�Ҳ���Դ���һ��iframeԪ�أ�Ȼ����iframe��ִ�в���JS���롣
�����ӳټ���
��ЩJS������ĳЩ�������Ҫʹ�ã�������ҳ���ʼ����ʱ���Ҫ�õ����ӳټ��ؾ���Ϊ�˽��������⡣��JS�зֳ����ģ�飬ҳ���ʼ��ʱֻ������Ҫ����ִ�е�JS��Ȼ������JS�ļ����ӳٵ���һ����Ҫ�õ���ʱ���ټ��ء�����ͼƬ���ӳټ��ء�
JS�ļ��ط�Ϊ�������֣����غ�ִ�С��첽����ֻ�ǽ�������ص����⣬���Ǵ�����������ɺ�ͻ�����ִ�У���ִ�й������������������״̬����Ӧ�����κ�����
���˼·��Ϊ�˽��JS�ӳټ��ص����⣬���������첽���ػ�����������������ִ�У���Ҫ��ʱ����ִ�С���ν��л����أ���JS������ΪImage����Object������ػ������������Բ�������ִ�У�Ȼ���ڵ�һ����Ҫ��ʱ����ִ�С�
    1��ģ��ϳ�������ʱ�䣺
    ����thread����sleepһ��ʱ����ִ�����ز�����
    2��ģ��ϳ���JS����ִ��ʱ��
    var start = Number(new Date());
    while(start + 5000 > Number(new Date())){//ִ��JS}
    ��δ��뽫ʹJSִ��5�����ɣ�
JS�ӳټ��ػ���(LazyLoad)������˵�������������������ĳ��λ���ڴ�����صĺ�����ʵ��ҳ��Ԫ�صļ��ػ���ĳЩ������ִ�С����ʵ�����������λ�õļ���أ�����ͨ��һ����ʱ����ʵ�֣�ͨ���Ƚ�ĳһʱ��ҳ��Ŀ��ڵ�λ�ú�������������߶����ж��Ƿ���Ҫִ�к�����