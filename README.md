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
