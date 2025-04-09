# 10questions


/*
١ برنامه ای بنویسید که دو عدد صحیح خیلͬ بزرگ را بͽیرد و با هم جمع کند. در اینجا منظور از عدد خیلͬ بزرگ اعداد
بیش از ٢٠ رقم هستند. شما باید دو عدد خیلͬ بزرگ را به صورت رشته دریافت کنید و جمع آن ها را محاسبه کنید.
دقت کنید که مجاز به استفاده از BigInterge نیستید.
 */
/* 
import java.util.Scanner;

class LargeNumberSum {
    public static String addLargeNumbers(String num1, String num2) {
        StringBuilder result = new StringBuilder();
        int carry = 0;
        int i = num1.length() - 1, j = num2.length() - 1;

        while (i >= 0 || j >= 0 || carry > 0) {
            int digit1 = (i >= 0) ? num1.charAt(i) - '0' : 0;
            int digit2 = (j >= 0) ? num2.charAt(j) - '0' : 0;
            int sum = digit1 + digit2 + carry;

            result.append(sum % 10);
            carry = sum / 10;

            i--;
            j--;
        }

        return result.reverse().toString();
    }
}

public class App {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("please enter 2 large numbers:");
        String num1 = scanner.next();
        String num2 = scanner.next();

        String sum = LargeNumberSum.addLargeNumbers(num1, num2);
        System.out.println("The sum of two numbers: " + sum);
    }
}
*/


/*٢ برنامه بنویسید که یͷ رشته را دریافت کند و تمام حروف تکراری آن را حذف کرده و فقط حروف یͺتای آن را نگه دارد.
مثلا اگر کاربر کلمه programming را وارد کرد کلمه programin را بازگرداند. */
/*
import java.util.LinkedHashSet;
import java.util.Scanner;

public class UniqueCharacters {
    public static String removeDuplicates(String input) {
        LinkedHashSet<Character> uniqueChars = new LinkedHashSet<>();
        StringBuilder result = new StringBuilder();

        for (char c : input.toCharArray()) {
            if (uniqueChars.add(c)) {
                result.append(c);
            }
        }

        return result.toString();
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Enter a string:");
        String input = scanner.nextLine();

        String output = removeDuplicates(input);
        System.out.println("String without duplicate characters:" + output);
    }
}
 */

/*٣ برنامه ای بنویسید که رشته ای شامل ()، {} و [] را دریافت کند و بررسͬ کند که آیا ترتیب آن ها درست است یا نه. */
 /*
import java.util.Stack;
import java.util.Scanner;

public class BracketValidator {
    public static boolean isValid(String s) {
        Stack<Character> stack = new Stack<>();

        for (char c : s.toCharArray()) {
            if (c == '(' || c == '{' || c == '[') {
                stack.push(c);
            } else if (c == ')' || c == '}' || c == ']') {
                if (stack.isEmpty())
                    return false;

                char top = stack.pop();
                if ((c == ')' && top != '(') ||
                        (c == '}' && top != '{') ||
                        (c == ']' && top != '[')) {
                    return false;
                }
            }
        }

        return stack.isEmpty();
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Enter a string {} , [] , () containing:");
        String input = scanner.nextLine();

        if (isValid(input)) {
            System.out.println(" The order of the parentheses is correct.!");
        } else {
            System.out.println(" The order of the parentheses is wrong.!");
        }
    }
}
  */


/*۴ برنامه ای که ١٠٠٠ بار پرتاب سͺه را شبیه سازی کند و درصد رخداد هر حالت (شیر یا خط) را نمایش دهد. برای این
کار از کتابخانه Random.util.java مͬ توانید استفاده کنید. */
  /*
import java.util.Random;

public class CoinFlipSimulation {
    public static void main(String[] args) {
        Random random = new Random();
        int headsCount = 0;
        int tailsCount = 0;
        int totalFlips = 1000;

        for (int i = 0; i < totalFlips; i++) {
            boolean isHeads = random.nextBoolean();
            if (isHeads) {
                headsCount++;
            } else {
                tailsCount++;
            }
        }

        double headsPercentage = (headsCount / (double) totalFlips) * 100;
        double tailsPercentage = (tailsCount / (double) totalFlips) * 100;

        System.out.println("The number of throws: " + totalFlips);
        System.out.println("Lion:" + headsCount + " load (" + headsPercentage + "%)");
        System.out.println("line:" + tailsCount + " load (" + tailsPercentage + "%)");
    }
}
   */



   /*۵ برنامه ای بنویسید که یͷ عدد را دریافت کند و بررسͬ کند که آیا مجموع نیمه اول و نیمه دوم ارقامش برابر است یا نه. */
    /*
   /*
import java.util.Scanner;

public class BalancedNumberCheck {
    public static boolean isBalancedNumber(String number) {
        int length = number.length();

        if (length % 2 != 0) {
            System.out.println("The number must have an even number of digits.!");
            return false;
        }

        int mid = length / 2;
        int sumFirstHalf = 0;
        int sumSecondHalf = 0;

        for (int i = 0; i < mid; i++) {
            sumFirstHalf += number.charAt(i) - '0';
            sumSecondHalf += number.charAt(mid + i) - '0';
        }

        return sumFirstHalf == sumSecondHalf;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("please entre number:");
        String number = scanner.next();

        if (isBalancedNumber(number)) {
            System.out.println("This number is balanced.!");
        } else {
            System.out.println("This number is not balanced.!");
        }
    }
}
    */


/*۶ برنامه ای که یͷ آرایه و دو مقدار از کاربر بͽیرد و کمترین فاصله عددی بین این دو مقدار را در آرایه محاسبه کند. */
     /*

    import java.util.Scanner;

public class MinDistanceFinder {
    public static int findMinDistance(int[] arr, int num1, int num2) {
        int minDistance = Integer.MAX_VALUE;
        int index1 = -1, index2 = -1;

        for (int i = 0; i < arr.length; i++) {
            if (arr[i] == num1) {
                index1 = i;
            } else if (arr[i] == num2) {
                index2 = i;
            }

            if (index1 != -1 && index2 != -1) {
                minDistance = Math.min(minDistance, Math.abs(index1 - index2));
            }
        }

        return (minDistance == Integer.MAX_VALUE) ? -1 : minDistance;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter the number of array elements:");
        int n = scanner.nextInt();
        int[] arr = new int[n];

        System.out.println("Enter the array numbers.:");
        for (int i = 0; i < n; i++) {
            arr[i] = scanner.nextInt();
        }

        System.out.println("Enter two values.:");
        int num1 = scanner.nextInt();
        int num2 = scanner.nextInt();

        int minDistance = findMinDistance(arr, num1, num2);
        if (minDistance != -1) {
            System.out.println("The shortest distance between" + num1 + "and" + num2 + " is equal to: " + minDistance);
        } else {
            System.out.println("One of the numbers in the array was not found.!");
        }
    }
}
     */


/*٧ برنامه ای که دو آرایه دریافت کند و بررسͬ کند که آیا تمام عناصر آنها بدون در نظر گرفتن ترتیب، یͺسان هستند. */
     /* 
    import java.util.Arrays;
import java.util.Scanner;

public class ArrayEqualityCheck {
    public static boolean areArraysEqual(int[] arr1, int[] arr2) {
        if (arr1.length != arr2.length) {
            return false;
        }

        Arrays.sort(arr1);
        Arrays.sort(arr2);

        return Arrays.equals(arr1, arr2);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter the number of elements in the first array:");
        int n1 = scanner.nextInt();
        int[] arr1 = new int[n1];

        System.out.println("Enter the numbers of the first array:");
        for (int i = 0; i < n1; i++) {
            arr1[i] = scanner.nextInt();
        }

        System.out.println("Enter the number of elements in the second array:");
        int n2 = scanner.nextInt();
        int[] arr2 = new int[n2];

        System.out.println("Enter the numbers of the second array:");
        for (int i = 0; i < n2; i++) {
            arr2[i] = scanner.nextInt();
        }

        if (areArraysEqual(arr1, arr2)) {
            System.out.println("Arrays are the same regardless of order!");
        } else {
            System.out.println("The arrays are not the same!");
        }
    }
}
      */


/*٨ برنامه ای که یͷ آرایه از اعداد صحیح را دریافت کند و تعداد تکرار هر عدد را نمایش دهد. */
      /*
    import java.util.HashMap;
import java.util.Scanner;

public class FrequencyCounter {
    public static void countOccurrences(int[] arr) {
        HashMap<Integer, Integer> frequencyMap = new HashMap<>();

        for (int num : arr) {
            frequencyMap.put(num, frequencyMap.getOrDefault(num, 0) + 1);
        }

        System.out.println("Number of repetitions of each number:");
        for (HashMap.Entry<Integer, Integer> entry : frequencyMap.entrySet()) {
            System.out.println(entry.getKey() + " → " + entry.getValue() + "load");
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter the number of array elements:");
        int n = scanner.nextInt();
        int[] arr = new int[n];

        System.out.println("Enter the array numbers:");
        for (int i = 0; i < n; i++) {
            arr[i] = scanner.nextInt();
        }

        countOccurrences(arr);
    }
}
       */



       /*٩ سیستم رای گیری را در نظر بͽیرید. فرض کنید ۵ کاندید داریم و ٢۵ شرکت کننده. هر نفر به یͷ کاندید مͬ تواند رای
بدهد یا برگه خالͬ بدهد. برنامه ای بنویسید که این رای گیری را انجام دهد. */
       /*
        import java.util.HashMap;
import java.util.Scanner;

public class VotingSystem {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        String[] candidates = { "Candidate 1", "Candidate 2", "Candidate 3", "Candidate 4", "Candidate 5" };
        HashMap<String, Integer> votes = new HashMap<>();

        for (String candidate : candidates) {
            votes.put(candidate, 0);
        }
        votes.put("white paper", 0);

        System.out.println("The voting system has begun!");
        for (int i = 1; i <= 25; i++) {
            System.out.println(
                    "Participant" + i + ": Please enter the candidate number (1 to 5) or 0 for a blank sheet:");
            int choice = scanner.nextInt();

            if (choice >= 1 && choice <= 5) {
                votes.put(candidates[choice - 1], votes.get(candidates[choice - 1]) + 1);
            } else if (choice == 0) {
                votes.put("white paper", votes.get("white paper") + 1);
            } else {
                System.out.println("Invalid selection! Please enter only numbers between 0 and 5.");
                i--;
            }
        }

        System.out.println("\nVoting results:");
        for (String candidate : votes.keySet()) {
            System.out.println(candidate + " → " + votes.get(candidate) + "vote");
        }
    }
}
        */




        /*٠ نوع خاصͬ از رای گیری وجود دارد به نام رای گیری .burda در این رای گیری شرکت کنندگان مͬ توانند ترجیحات خود را
برای کاندیداها بنویسند. مثلا فرض کنید ۵ کاندید وجود دارد. شرکت کنندگان در برگه رای خود به جای یͷ نفر ترجیحات
حال E،B،A،C،D. رͽدی شخص ͷی B،C،E،A،D. رͽدی شخص ͷی B،A،E،C،D. نمونه برای .نویسند ͬم را خود
اگر امتیاز کاندیداها را حساب کنیم A ٩ امتیاز کسب مͬ کند. B ١۴ امتیاز، C ٨ امتیاز، D ٣ امتیاز و E ١١ امتیاز. به
این ترتیب B برنده خواهد شد. برنامه ای بنویسید که این فرایند رای گیری را انجام دهد. تعداد کاندیداها را ۵ در نظر
بͽیرید و تعداد شرکت کنندگان را . */
        /*
         import java.util.HashMap;
import java.util.Scanner;

public class BordaVotingSystem {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        String[] candidates = { "A", "B", "C", "D", "E" };
        HashMap<String, Integer> scores = new HashMap<>();

        for (String candidate : candidates) {
            scores.put(candidate, 0);
        }

        System.out.println("The Borda voting system has begun! Please enter your preferences for 5 candidates.");
        for (int i = 1; i <= 25; i++) {
            System.out.println("Participant" + i + "Please enter your order of preference (eg: B A E C D):");
            String[] preferences = scanner.nextLine().split(" ");

            for (int j = 0; j < preferences.length; j++) {
                scores.put(preferences[j], scores.get(preferences[j]) + (5 - j));
            }
        }

        System.out.println("\nVoting results based on the Borda method:");
        String winner = "";
        int maxScore = 0;
        for (String candidate : scores.keySet()) {
            System.out.println(candidate + " → " + scores.get(candidate) + "score");
            if (scores.get(candidate) > maxScore) {
                maxScore = scores.get(candidate);
                winner = candidate;
            }
        }

        System.out.println("\nElection winner:" + winner + "with" + maxScore + " score!");
    }
}
         */
