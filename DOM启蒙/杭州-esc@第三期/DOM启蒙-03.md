# ��Dom���ɡ�����ʼ�

## ��1�� �ڵ����

2.1 �ĵ��ڵ����
2.2 HTML �ĵ������뷽���������̳еģ�
2.3 ��ȡ HTML Document ͨ����Ϣ�����⡢���ӡ��ἰ�ߡ�����޸�ʱ�估����ģʽ��
2.4 �ĵ��ӽڵ�
2.5 document �ṩ�� <!DOCTYPE>��<html lang="en">��<head>�� <body> �ݾ�
2.6 ʹ�� document.implementation.hasFeature() ̽�� DOM �淶/����
2.7 ��ȡ�ĵ��е�ǰ�۽�/����ڵ������
2.8 �ж��ĵ������ĵ����κνڵ�õ�����
2.9 document.defaultView �Ǹ�������/ȫ�ֶ���Ľݾ�
2.10 ʹ�� ownerDocument ��ĳһԪ��ȡ���ĵ�������

## Ԫ�ؽڵ�

> ÿ��HTML Ԫ����Ԫ�ؽڵ� HTML Ԫ���ڵ��ı����ı��ڵ� 
### ������ʾ
	
	��html lang=""en""��
		��body��
			<table>   
			  <tr>   
			    <td id="john" name="myname">John</td>   
			    <td>Doe</td>  
			    <td id="jack">Jack</td>   
			  </tr>   
            </table>
         <script>   
	  var d = document.getElementById("john").getAttributeNode("name");     
             alert(d.nodeType)   
             alert(d.nodeName)   
             alert(d.nodeValue)     
          </script>   
		��/body��
	��/html��



## Ԫ�ؽڵ�ѡȡ
> ѡȡ�ض�Ԫ�ؽڵ�
> - querySelector()
> - getElementById()
> 
> ѡȡ/�����ڵ��б�
> - querySelectorAll()
> - getElementsByTagName()
> - getElementByClassName()
> 
>ѡȡ�ӽڵ�
>- children
> 
>ѡȡ�������й�Ԫ��
>- querySelector()
>- querySelectorAll()
>- getElementsByTagName()
>- getElementsByClassName()����
