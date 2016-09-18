# algorithms
## 简单的排序算法：BubbleSort、SelectSort、InsertSort;
- BubbleSort
```
public class ArrayBub {
    private long[] a;
    private int nElems;

    public ArrayBub(int max) {
        a=new long[max];
        nElems=0;
    }
    public void insert(long value){
        a[nElems]=value;
        nElems++;
    }
    public void display(){
        for (int j=0;j<nElems;j++){
            System.out.print(a[j]+"");
            System.out.println("");
        }
    }
    public void bubbleSort(){
        int out ,in;

        for (out=nElems-1;out>1;out--)
            for (in=0;in<out;in++)
                if (a[in]>a[in+1])
                    swap(in,in+1);

    }

    private void swap(int one, int two) {
        long temp=a[one];
        a[one]=a[two];
        a[two]=temp;

    }
}

public class BubbleSort {
    public static void main(String[] args){
        int maxSize=100;
        ArrayBub arr;
        arr=new ArrayBub(maxSize);

        arr.insert(12);
        arr.insert(17);
        arr.insert(25);
        arr.insert(1);
        arr.insert(56);
        arr.insert(5);
        arr.insert(25);
        arr.insert(13);
        arr.insert(47);
        arr.insert(26);

        arr.display();
        System.out.println("--------------------------------------------");

        arr.bubbleSort();
        arr.display();
    }
}

```
- SelectSort
```
public class ArraySel {
    private long[] a;
    private int nElems;

    public ArraySel(int max) {
        a=new long[max];
        nElems=0;
    }
    public void insert(long value){
        a[nElems]=value;
        nElems++;
    }
    public void display(){
        for (int j=0;j<nElems;j++){
            System.out.print(a[j]+"");
            System.out.println("");
        }
    }
    public void SelectSort(){
        int out,in,min;
        for (out=0;out<nElems-1;out++){
            min=out;
            for(in=out+1;in<nElems;in++)
                if (a[in]<a[min])
                    min=in;
            swap(out,min);
        }
    }

    private void swap(int one, int two) {
        long temp=a[one];
        a[one]=a[two];
        a[two]=temp;

    }
}

public class SelectSort {
    public static void main(String[] args){
        int maxSize=100;
        ArraySel arr;
        arr=new ArraySel(maxSize);

        arr.insert(12);
        arr.insert(17);
        arr.insert(25);
        arr.insert(1);
        arr.insert(56);
        arr.insert(5);
        arr.insert(25);
        arr.insert(13);
        arr.insert(47);
        arr.insert(26);

        arr.display();
        System.out.println("--------------------------------------------");

        arr.SelectSort();
        arr.display();
    }
}
```
- InsertSort
```
<!--局部有序（区别于冒泡和选择排序）-->
public class ArrayIns {
    private long[] a;
    private int nElems;

    public ArrayIns(int max) {
        a=new long[max];
        nElems=0;
    }
    public void insert(long value){
        a[nElems]=value;
        nElems++;
    }
    public void display(){
        for (int j=0;j<nElems;j++){
            System.out.print(a[j]+"");
            System.out.println("");
        }
    }
    public void insertSort(){
        int in,out;

        for (out=1;out<nElems;out++){
            long temp=a[out];
            in=out;
            while(in>0&&a[in-1]>=temp){
                a[in]=a[in-1];
                --in;
            }
            a[in]=temp;

        }
    }
}


public class InsertSort {
    public static void main(String[] args){
        int maxSize=100;
        ArrayIns arr;
        arr=new ArrayIns(maxSize);

        arr.insert(12);
        arr.insert(17);
        arr.insert(25);
        arr.insert(1);
        arr.insert(56);
        arr.insert(5);
        arr.insert(25);
        arr.insert(13);
        arr.insert(47);
        arr.insert(26);

        arr.display();
        System.out.println("--------------------------------------------");

        arr.insertSort();
        arr.display();
    }
}

```

## 二分法查找
```
基本原理：每次查找都对半分，但要求数组是有序的

public class Solution {

    public static int BinarySearch(int[] sz,int key){
        int low = 0;
        int high = sz.length - 1;

        while (low <= high) {
            int middle = (low + high) / 2;
            if(sz[middle] == key){
                return middle;
            }else if(sz[middle] > key){
                high = middle - 1;
            }else {
                low = middle + 1;
            }
        }
        return -1;
    }
}
```

## 栈和队列
- 栈

 讲究后进先出，栈只允许访问一个数据项（即最后插入的数据项）

- 队列

 讲究先进先出；
 
 ```
 用两个栈来实现一个队列，完成队列的Push和Pop操作。 队列中的元素为int类型。（来自剑指offer）
 
 import java.util.Stack; //使用栈记得引用java.util,Stack包
 
public class Solution {
   Stack<Integer> stack1 = new Stack<Integer>();
   Stack<Integer> stack2 = new Stack<Integer>();
   
//入栈函数
   public void push(int num) {
       stack1.push(num);    //要往栈中压入什么就直接用栈的push方法就好了      
    }
   
//出栈函数
   public int pop() {
   Integer re=null; 
       if(!stack2.empty()){  // 如果栈2不是空的，那么把最上面那个取出来
           re=stack2.pop(); 
       }else{ 
               //如果栈2是空的，就把栈1里的数一个个取出来，放到栈2里
           while(!stack1.empty()){   
                re=stack1.pop(); 
                stack2.push(re); 
                             } 
                  //栈2里有数之后，再次把里面的数取出来
                  if(!stack2.empty()){ 
                         re=stack2.pop(); 
                   } 
       } 
       return re; 
    }
}
 ```

- 优先级队列

## 链表

  在有序链表中插入数据项的方法：当算法找到了要插入的位置时，把新链结点的next字段指向下一个链结点，然后把前一个链结点的next字段改为指向新的链结点，链结点插在表头或者表尾另说；
  
- 输入一个链表，从尾到头打印链表每个节点的值。 (来自剑指offer)
```
import java.util.ArrayList;
public class Solution {
    ArrayList<Integer> arrayList=new ArrayList<Integer>();
    public ArrayList<Integer> printListFromTailToHead(ListNode listNode) {
        if(listNode!=null){
            this.printListFromTailToHead(listNode.next);
            arrayList.add(listNode.val);
        }
        return arrayList;
    }
}
```
 
