```java
/*
정수 n이 주어지면, n개의 여는 괄호 "("와 n개의 닫는 괄호 ")"로 만들 수 있는 괄호 조합을 모두 구하시오. (시간 복잡도 제한 없습니다).
Given an integer N, find the number of possible balanced parentheses with N opening and closing brackets.

예제)
Input: 1
Output: ["()"]

Input: 2
Output: ["(())", "()()"]

Input: 3
Output: ["((()))", "(()())", "()(())", "(())()", "()()()"]
 
 */


import java.util.ArrayList;
import java.util.List;


public class problem3 {
	public static List<String> parenthesisParis(int n) {
		List<String> ans = new ArrayList<>();
		recurse(ans, "", 0, 0, n);
		return ans;
	}
	
	
	private static void recurse(List<String> ans, String str, int open, int close, int n) {
		if(str.length() == n * 2) {
			ans.add(str);
		}
		if(open < n) {
			recurse(ans, str + "(", open + 1, close, n);
		}
		if(close < open) {
			recurse(ans, str + ")", open, close + 1, n);
		}
		
	}


	public static void main(String[] args) {
		
		System.out.println(parenthesisParis(3));

	}

}
```
