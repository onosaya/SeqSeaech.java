# SeqSeaech.java
番兵法
import java.util.Scanner;
public class SeqSearch {

	static int search(int[] a, int n, int key) { // 線形探索関数
		int i = 0;
		
		a[n] = key; // 番兵を配列に追加
		while (true) {
			if (a[i] == key) break; // 探索成功
			i++;
		}
		return i == n ? ‐1 : i; // 探索失敗は(‐1)，成功は位置を返す
	}

	public static void main(String[] args) {
		Scanner stdIn = new Scanner(System.in);
		
		System.out.print("要素数："); // 入力のための見出し
		int num = stdIn.nextInt(); // 要素数の読み込み
		int[] x = new int[num+1]; // 番兵のため要素数+1の配列を確保
		
		for (int i = 0; i < num; i++) { // データの読み込み
			System.out.print("x["+i+"]：");
			x[i] = stdIn.nextInt();
		}
		
		System.out.print("探す値："); // キー値の読込み
		int ky = stdIn.nextInt();
		
		int idx = search(x, num, ky); // 線形探索
		
		if (idx == ‐1) // 結果の表示
			System.out.println("その値はありません．");
		else
			System.out.println("その値はx["+idx+"]にあります．");
	}
}
