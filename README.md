<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<title>���鷽��</title>

<script>


var arr1 = new Array(); //����һ��������
var arr2 = new Array(20); // ����һ������20������� [������Ԫ�ض��ǿ�]
var arr3 = new Array("lily","lucy","Tom"); // ����һ������3���ַ���������

join()
push()��pop()
shift() �� unshift()
sort()
reverse()
concat()
slice()
splice()
indexOf()�� lastIndexOf() ��ES5������
forEach() ��ES5������
map() ��ES5������
filter() ��ES5������
every() ��ES5������
some() ��ES5������
reduce()�� reduceRight() ��ES5������


join();// �������Ԫ������һ���ַ���

push()  β����ӣ� unshift() ͷ�����  pop() β��ɾ�� shift() ͷ��ɾ��

sort();  //������ʱ��sort()���������ÿ��������� toString()ת�ͷ�����Ȼ��Ƚϵõ����ַ�������ȷ��������򡣼�ʹ�����е�ÿһ�����ֵ�� sort()�����Ƚϵ�Ҳ���ַ���.
    sort��������������
    let arr = [3,9,1,3,4,6,5];
    arr.sort(function(a,b){
        return a-b;  //С����  b-a ��С
    });
    console.log(arr); 


reverse();  //��ת�������˳��
    var arr = [13, 24, 51, 3];
    console.log(arr.reverse()); //[3, 51, 24, 13]
    console.log(arr); //[3, 51, 24, 13](ԭ����ı�)



concat(); // ��������ӵ�ԭ�����С�����������ȴ�����ǰ����һ��������Ȼ�󽫽��յ��Ĳ�����ӵ����������ĩβ����󷵻��¹��������顣��û�и� concat()�������ݲ���������£���ֻ�Ǹ��Ƶ�ǰ���鲢���ظ�����
    var arr = [1,3,5,7];
    var arrCopy = arr.concat(9,[11,13]);
    console.log(arrCopy); //[1, 3, 5, 7, 9, 11, 13]
    console.log(arr); // [1, 3, 5, 7](ԭ����δ���޸�)


Array.slice(); ���ش�ԭ������ָ����ʼ�±굽�����±�֮�������ɵ�������
var arr = [1,3,5,7,9,11];
    console.log(arr.slice(1));  //[3,,5,7,9,11] 
    console.log(arr.slice(1,4));  //[3,5,7] //����������λ��
    console.log(arr.slice(1,-2)); //[3,5,7]
    console.log(arr.slice(-1,2));  //�൱��(5,2)Ϊ��

    arrCopy3������������������ֹ�±�Ϊ�����������ָ���ʱ���������������鳤�ȵ�ֵ��6�����滻��λ�õ�������˾��Ǵ�1��ʼ��4�����������������顣 
    arrCopy4�������������Ǹ��������Զ��������鳤��6ת��������������൱��slice(2,5)��




Array.splice();// ɾ�����滻����ӡ�
    let arr = [1,3,5,7,9];
    console.log(arr.splice(1,2),arr);[3,5],[1,7,9] //ɾ��  1��������ʼλ�ã�2������ɾ��������
    console.log(arr.splice(1,1,'���'),arr);[3],[1,'���',5,7,9]  //�滻  1��������ʼλ�ã�2������ɾ��������3�������滻�
    console.log(arr.splice(1,0,'���','�Һ�'),arr);[],[1,'���','�Һ�',3,5,7,9]   //���  1��������ʼλ�ã�0������ɾ��������3�����ǲ����



Array.indexOf()�� indexOf�����ж�NaN
        ��������������Ҫ���ҵ���ͣ���ѡ�ģ���ʾ�������λ�õ����������У� ������Ŀ�ͷ��λ�� 0����ʼ�����ҡ� 
Array.lastIndexOf��
        ��������������Ҫ���ҵ���ͣ���ѡ�ģ���ʾ�������λ�õ����������У� �������ĩβ��ʼ��ǰ���ҡ�    
        var arr = [1,3,5,7,9,11];
        console.log(arr.indexOf(5)); //û��ƥ�䵽�ͷ���-1,ƥ�䵽�ͷ���ƥ��ֵ��λ�á�

Array.inculudes:���õ�ͬindexOf();
    1.�������ķ���ֵ��indexOf���ص�����ֵ�͵Ķ�includes���ص��ǲ����͵�
    2.������֧�ֵڶ����������ҵĵڶ���������֧�ָ�����ʽ
    3.�����е�indexOf�����ж��������Ƿ���NaN��includes����.
    var arr = [NaN];
    console.log(arr.indexOf(NaN)); //-1  �����ж�NaN
    console.log(arr.includes(NaN)); //true  �����ж�NaN

    var arr1 = [,,]; //ϡ������  indexOf ��Ϊϡ�����飬ʡ�Ե���ֵ�ǲ����ڵģ��� includes ��Ϊ��undefined
    console.log(arr.indexOf(undefined)); // -1
    console.log(arr.includes(undefined)); // true



Array.forEach()  Array.map() 
     ��ͬ�㣺
         1.����ѭ�����������е�ÿһ�
         2.forEach() �� map() ����ÿһ��ִ������������֧��3�������������еĵ�ǰ��item,��ǰ�������index,ԭʼ����input��
         3.���������е�this����ָWindow��
         4.ֻ�ܱ������顣

Array.forEach() => û�з���ֵ 
Array.map()     => �з���ֵ������return����   
    var ary = [12,23,24,42,1];
    var res = ary.forEach(function (item,index,input) {
        input[index] = item*10;
    })
    console.log(res);   //-->undefined;
    console.log(ary);   //-->���ԭ������������ı䣻

    var ary = [12,23,24,42,1];
    var res = ary.map(function (item,index,input) {
    ? ? return item*10;
    })
    console.log(res);   //-->[120,230,240,420,10];
    console.log(ary);   //-->[12,23,24,42,1];



Array.filter()  �����ˡ����ܣ������е�ÿһ�����и��������������������������ɵ����顣
    var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
    var arr2 = arr.filter(function(x, index) {
        console.log(x,index); //x��������ÿһ�index�Ƕ�Ӧ���±�
        return index % 3 === 0 || x >= 8;
    }); 
    console.log(arr2); //[1, 4, 7, 8, 9, 10];



Array.every()   �ж�������ÿһ��Ƿ�����������ֻ������������������Ż᷵��true��

    var arr = [1, 2, 3, 4, 5];
    var arr2 = arr.every(function(x) {
        return x < 10;
    }); 
        console.log(arr2); //true

    var arr3 = arr.every(function(x) {
        return x < 3;
    }); 
        console.log(arr3); // false




Array.some()  �ж��������Ƿ���������������ֻҪ��һ�������������ͻ᷵��true��

    var arr = [1, 2, 3, 4, 5];
    var arr2 = arr.some(function(x) {
        return x < 3;
    }); 
        console.log(arr2); //true

    var arr3 = arr.some(function(x) {
        return x < 1;
    }); 
        console.log(arr3); // false





Array.reduce() 
1.�﷨�� arr.reduce(callback,[initialValue]);  /Ϊ������ÿ��Ԫ�ض�ִ�лص�������
callback����4��������ִ��������ÿ��ֵ�ĺ����������ĸ�������
    1��previousValue ����һ�ε��ûص����ص�ֵ���������ṩ�ĳ�ʼֵ��initialValue����
    2��currentValue �������е�ǰ�������Ԫ�أ�
    3��index ����ǰԪ���������е�������
    4��array ������ reduce �����飩
    ʾ����
    let arr = [1,2,3,4,5];
    ���÷�
    let sum = arr.reduce((prev,cur)=>{
        return prev + cur;
    },0);   //���������ʱ����ʼinitialValue������0  
    console.log(sum,arr);
    let sum = arr.reduce((prev,cur) => prev+cur);
    console.log(sum,arr);

    �߼��÷���
    1.����ȥ��
    let arr = [1,2,3,4,4,1];
    let newArr = arr.reduce((pre,cur)=>{
        if(!pre.includes(cur)){
            return pre.concat(cur);
        }else{
            return pre;
        }
    },[]);  //�������ʱ����ʼinitialValue�ǿ����飬�������ʱ���ǿն���
    console.log(newArr);

    2.��ά�����ƽ��
    let arr = [[1,2],3,4,[5,6]];
    let newArr= arr.reduce((pre,cur)=>{
        return pre.concat(cur);
    },[]);
    console.log(newArr,arr);

    3.��ά�����ƽ��
    let arr=[[1,2],[3,[4,5],6,[7,8]],9];
    let newArr = (arr)=>{
        return arr.reduce( (pre,cur)=> pre.concat( Array.isArray(cur)?newArr(cur):cur ),[] );   //��ͷ��������{}��������ֱ��Я��return����
    };
    let newArr = (arr)=>{
        return arr.reduce((pre,cur)=>{
            return pre.concat(Array.isArray(cur) ? newArr(cur):cur)
        },[]);
    }
    console.log(newArr(arr));

    4.����ȥ��
    let arr = [1,2,3,4,4,1];
    let newArr = arr.reduce((pre,cur) => {
        if( !pre.includes(cur) ){
            return pre.concat(cur);
        }else{
            return pre;
        }
    },[]);
    console.log(newArr);


    5.����������ÿ��Ԫ�س��ֵĴ�����
    let arr = [1,2,3,4,4,1];
    let newArr = arr.reduce( (pre,cur)=>{
        if(cur in pre ){
            pre[cur]++;
        }else{
            pre[cur]=1;
        }
        return pre;
    }, {} );
    console.log(newArr);

    6.�������������
    let result = [
        {
            subject: 'math',
            score: 10
        },
        {
            subject: 'chinese',
            score: 20
        },
        {
            subject: 'english',
            score: 30
        }
    ];

    var sum = result.reduce(function(pre,cur){
        return cur.score+ pre;
    },0); 
    console.log(sum);



�ַ�����indexOf�������е�indexOf�ıȽ�
    1.���������������Խ�����������
    2.������������û�в��ҵ�ָ�����ַ�������-1
    3.�ַ����е�indexOf�еĵڶ���������֧�ָ����������indexOf֧��
    4.�ַ�����indexOf�ڴ�����������ַ����������Ĭ�ϻ�ת��Ϊ�ַ����������indexOf��������������ת��

�ַ�����includes�������е�includes�ıȽ�
    1.���������������Խ�����������
    2.������������û�в��ҵ�ָ�����ַ�������false
    3.�ַ����е�includes�еĵڶ���������֧�ָ����������includes֧��
    4.�ַ�����includes�ڴ�����������ַ����������Ĭ�ϻ�ת��Ϊ�ַ����������includes��������������ת��

�ַ�����slice�������е�slice�ıȽ�
    1.�ڲ������κβ���������¶��ǰ�ԭ����ֵ����һ��
    2.�ַ�����slice�ĵڶ��������ǲ�֧�ָ����Ķ�����Ŀ���
    3.�����Խ�����������



</script>
</head>

<body>
</body>
</html>
