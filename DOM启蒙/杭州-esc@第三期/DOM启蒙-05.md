# ��Dom���ɡ�����ʼ�


## ��8�� DocumentFragment�ڵ�

> ��Ϊ��ʵʱDOM����£��������ڴ��д��ڣ����������ӽڵ���Լ򵥵����ڴ��в��������󸽼ӵ�ʵʱDOM

##ʹ��createDocumentFragment()����DocumentFragment
    

    <script>
      
        var docFrag = document.createDocumentFragment();

		["blue","green","red","blue","pink"].forEach(function(e){
			var li = document.createElement("li");
			li.textContent = e;
			docFrag.appendChild(li);
		}) 
		
		
        console.log(docFrag .textContent); //���text()
      
    </script>

>ʹ���ĵ�Ƭ�����ڴ��д����ڵ�ṹ��ע����ĵ�Ƭ�ε�ʱʵ�ڵ�ṹʱ���Ǽ����Ч�ģ�����
>
## ���DocumentFragment��ʵʱDOM
> appendChild()��insertBefore()����ʱ���ĵ�Ƭ�ε��ӽڵ㽫�������Ϊ������Щ������DOM�ڵ���ӽڵ㡣


##ʹ���ĵ�Ƭ���ϵ�innerHTML
> �������ı��ڵ㣬�������ļ��������ǿհ��ı��ڵ����⡣IE8-�������ʶ��հ��ı�

##ͨ�����Ʊ������ڴ���
> ʹ��cloneNode()���ڸ����ĵ�Ƭ��ʱ���Ƽ���