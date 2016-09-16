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

## 栈和队列
- 栈

 讲究后进先出，栈只允许访问一个数据项（即最后插入的数据项）

- 队列

 讲究先进先出；

- 优先级队列

## 链表
 
