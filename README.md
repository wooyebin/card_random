//import java.util.Scanner;

public class RandomCard {
	public static void main(String args[]){
		//Scanner sc = new Scanner(System.in);
		char[] mark = {'h', 'd', 'c', 's'};
		char[] num = {'a', '2', '3', '4', '5', '6', '7', '8', '9', 'j', 'q', 'k'};
		int[][] check = new int[2][5];
		boolean right = true;
		boolean markRight = true;
		boolean numRight = true;
		
		while(right){
			markRight = true;
			numRight = true;
			for(int i=0; i<5; i++){
				int randomMark = (int)(Math.random()*4);
				int randomNum = (int)(Math.random()*12);
				check[0][i] = randomMark;
				check[1][i] = randomNum;
			}
			
			for(int i=1; i<5; i++){
				if(check[0][0] != check[0][i]){
					markRight = false;
				}
				if(check[1][i-1]+1 != check[1][i]){
					numRight = false;
				}
			}
			if(markRight && numRight){
				for(int i=1; i<5; i++){
					System.out.println(mark[check[0][i]]+" "+num[check[1][i]]);
				}
				right = false;
			}
		}
		
	}
}
