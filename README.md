# test
笔试题
求解一个脉冲函数的先升后降最大区间
<pre><code>
public class Test {

    public void Sort(int[] number) {
        int[] arry = new int[number.length - 1];
        int count = 0;
        int max = 0;
        int start = 0;
        for (int i = 0; i < number.length - 1; i++) {
            if (i == 0) {
                if (number[i] < number[i + 1]) {
                    arry[count] = i;
                    count++;
                }
            } else {
                if (i == number.length - 2) {
                    arry[count] = i;
                    count++;
                } else {
                    if (number[i] < number[i + 1] && (number[i] < number[i - 1])) {
                        arry[count] = i;
                        count++;
                    }
                }
            }
        }
        for (int j = 0; j < arry.length - 1; j++) {
            if (arry[j] == 0) {

            } else {
                if ((arry[j] - arry[j - 1]) > max) {
                    max = arry[j] - arry[j - 1];
                    start = arry[j - 1];
                }
            }
        }
        if (start == 0 && max == 0) {
            System.out.println("最大区间为:" + "-1" + "到" + "-1");
        } else {
            System.out.println("最大区间为:" + start + "到" + (start + max + 1));
        }
    }

    public static void main(String[] args) {
        Test test = new Test();
        int[] arry = {3,44,55,66,9,8,7,6,5,4,3,2};
        test.Sort(arry);
    }
}
</pre></code>
2.
a对应0 z对应25 26进制数  输出二十六进制对应的10进制数







<pre><code>
public class Main {
    public void numberTen(String s, HashMap map) {
        char[] c= s.toCharArray();
        int sum=0;
        for(int i=0;i<c.length;i++){
            sum=sum+((int)map.get(c[i]))*26;
        }
        System.out.print("相对应的10进制数是:"+sum);
    }

    public static void main(String[] args) {
        int count=0;
        HashMap m = new HashMap();
        for(int i=97;i<123;i++){
            m.put((char)i,count);
            count++;
        }
        Main main=new Main();
        Scanner scan=new Scanner(System.in);
        String test=scan.next();
        main.numberTen(test,m);

    }
}
</code></pre>
