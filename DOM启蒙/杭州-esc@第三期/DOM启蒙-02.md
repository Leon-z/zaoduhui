# ��Dom���ɡ�����ʼ�

## ��1�� �ڵ����

- 1.1 �ĵ�����ģ�ͣ�Document Object Model����� DOM���Ǹ���JavaScript�ڵ�������- ��-��νṹ/��
- 1.2 �ڵ��������
- 1.3 �̳��Խڵ������ӽڵ����
- 1.4 ������ڵ�򽻵��������뷽��
- 1.5 ʶ��ڵ������������
- 1.6 ��ȡ�ڵ��ֵ
- 1.7 ʹ�� JavaScript ����������Ԫ�����ı��ڵ�
- 1.8 ʹ�� JavaScript �ַ�����������DOM�����Ԫ�����ı��ڵ�
- 1.9 ��ȡDOM���еĲ�����ΪJavaScript�ַ���
- 1.10 ʹ�� appendChild() �� insertBefore() ��DOM�в���ڵ����
- 1.11 ʹ�� removeChild() �� replaceChild() ���Ƴ����滻�ڵ�
- 1.12 ʹ�� cloneNode() �����ƽڵ�
- 1.13 ���ڵ㼯�ϣ��� NodeList �� HTMLCollection��
- 1.14 ��ȡ����ֱ���ӽڵ���б�/����
- 1.15 �� NodeList ���� HTMLCollection ת����JavaScript ����
- 1.16 ���� DOM �еĽڵ�
- 1.17 ʹ�� contains() �� compareDocumentPosition()��֤�ڵ��� DOM ���е�λ��
- 1.18 �ж������ڵ��Ƿ���ͬ

## ��2�� �ĵ��ڵ�

- 2.1 �ĵ��ڵ����
- 2.2 HTML �ĵ������뷽���������̳еģ�
- 2.3 ��ȡ HTML Document ͨ����Ϣ�����⡢���ӡ��ἰ�ߡ�����޸�ʱ�估����ģʽ��
- 2.4 �ĵ��ӽڵ�
- 2.5 document �ṩ�� <!DOCTYPE>��<html lang="en">��<head>�� <body> �ݾ�
- 2.6 ʹ�� document.implementation.hasFeature() ̽�� DOM �淶/����
- 2.7 ��ȡ�ĵ��е�ǰ�۽�/����ڵ������
- 2.8 �ж��ĵ������ĵ����κνڵ�õ�����
- 2.9 document.defaultView �Ǹ�������/ȫ�ֶ���Ľݾ�
- 2.10 ʹ�� ownerDocument ��ĳһԪ��ȡ���ĵ�������



## ͨ��F12�鿴��������

> DOM��Ŀ����ʹ��JS����(ɾ������ӡ��滻�������¼����޸�)Ϊ��ǰ�ĵ��ṩһ����ɽӿ�
### ������ʾ
	
	��html lang=""en""��
		��body��
			��script��
				��// �����´�����ص�ע��
				��var foo = ����;
			��/script��
		��/body��
	��/html��

## DOM�ڵ��Ϊ���ĵ��ڵ㡢Ԫ�ؽڵ㡢���Խڵ���ı��ڵ㡣

## �ڵ����ԣ�
>nodeName���ڵ����ơ�
nodeValue���ڵ��ֵ��
parentNode���ڵ�ĸ��ڵ㡣ÿ��Ԫ�ء����Ժ��ı�����һ�����ڵ㡣
childNodes���ڵ�ĺ��ӽڵ��б�����HTML�����б����Ԫ�������壬�ı��ڵ�����Խڵ㶼û�к��ӡ�
firstChild��������childNodes�б��е�һ���ڵ�Ŀ�ݷ�ʽ��
lastChild����һ�ֿ�ݷ�ʽ����ʾchildNodes�б��е����һ���ڵ㡣
previousSibling�����ص�ǰ�ڵ�֮ǰ�Ľڵ㡣���仰˵�������ص�ǰ�ڵ�ĸ��ڵ�� childNodes �б���λ�ڸýڵ�ǰ����Ǹ��ڵ㣨����е��Ի����¶�ǰ��һ�䣩��
nextSibling��������previousSibling���ԣ����ظ��ڵ��childNodes�б��е���һ���ڵ㡣
attributes��������Ԫ�ؽڵ㣬����Ԫ�ص������б�

##�ڵ㷽����
> insertBefore(newChild, referenceNode)��newChild�ڵ���뵽referenceNode֮ǰ��ע�⣬Ӧ�ö�newChild ��Ŀ�길�ڵ���ø÷�����
replaceChild(newChild, oldChild)��newChild�ڵ��滻oldChild�ڵ㡣
removeChild(oldChild)�����и÷����Ľڵ���ɾ��oldChild�ڵ㡣
appendChild(newChild)��newChild��ӵ����иú����Ľڵ�֮�С�newChild����ӵ�Ŀ��ڵ㺢���б��е�ĩ�ˡ�
hasChildNodes()�ڵ��ø÷����Ľڵ��к���ʱ�򷵻�true�����򷵻�false��
hasAttributes()�ڵ��ø÷����Ľڵ�������ʱ�򷵻�true�����򷵻�false��
 
##�ĵ��ڵ㣺
> Ҳ��ʹ��document���󴴽��½ڵ㣬������ʾ��
createElement(elementName)ʹ�ø��������ƴ���һ��Ԫ�ء�
createTextNode(text)ʹ���ṩ���ı�����һ���µ��ı��ڵ㡣
createAttribute(attributeName) ���ṩ�����ƴ���һ�������ԡ�

##Ԫ�ؽڵ㣺
> �����Դ����йصķ�����
getAttribute(name)������Ϊname������ֵ��
removeAttribute(name)ɾ����Ϊname�����ԡ�
setAttribute(name, value)����һ����Ϊname�����Բ�����ֵ��Ϊvalue��
getAttributeNode(name)������Ϊname�����Խڵ㡣
removeAttributeNode(node)ɾ����ָ���ڵ�ƥ������Խڵ㡣
�����Ƕ��Ԫ���йصķ�����
getElementsByTagName(elementName)���ؾ���ָ�����Ƶ�Ԫ�ؽڵ��б�

##�ı��ڵ㣺
>appendData(text)���ṩ���ı�׷�ӵ��ı��ڵ����������֮��
insertData(position, text)�������ı��ڵ���м�������ݡ���ָ����λ�ò����ṩ���ı���
replaceData(position, length, text)��ָ��λ�ÿ�ʼɾ��ָ�����ȵ��ַ������ṩ���ı�����ɾ�����ı���

##DOM �ڵ����Ͷ�����һЩ���������磺
>Node.ELEMENT_NODE �Ǳ�ʾԪ�ؽڵ����͵ĳ�����
Node.ATTRIBUTE_NODE �Ǳ�ʾ���Խڵ����͵ĳ�����
Node.TEXT_NODE �Ǳ�ʾ�ı��ڵ����͵ĳ�����
Node.DOCUMENT_NODE �Ǳ�ʾ�ĵ��ڵ����͵ĳ�����
	
