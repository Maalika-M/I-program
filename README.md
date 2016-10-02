# I-program
import java.util.*;
import java.math.*;
import java.util.regex.*;
import java.util.ArrayList;

public class Array2d {
	public static void main(String[] args) {
		int [] arr = {0,1,0,0,0,1,0,1,0,1,0,1,0,0,0,0};
		int m = 2;
		if (win(arr,m,0,0)) { 
			System.out.println("Yes");
			}
			else {
			System.out.println("No");
			}
		}
	static boolean win(int[] a, int m, int i, int j) {
		boolean v = false;
		if ((i+m)>(a.length-1)) {
			System.out.println("Success");
			return true;
			}
		if (i != 0) {
			if (a[i+1] == 1 && a[i-1] == 1 && a[i+m] == 1) {return false;}
			}
		if (a[i+m] == 0) {
			v = win(a,m,i+m,i);
			}
		if (a[i+1] == 0) {
			v = win(a,m,i+1,i);
			}
		if (i != 0) {
			if (a[i-1] == 0) {
				if (i-1 == j) {return false; break;}
				v = win(a,m,i-1,i);
			}
		}
		return v;
	}
}
