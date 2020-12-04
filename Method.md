# JAVA Methods
- JAVA Method는 **Class Method** 와 **Instance Method** 로 구분된다.
    - **Class Method** 는 함수 선언할 때에 `static` 이 붙은 method
    - **Instance Method** 는 `static`이 붙지 않은 method


## Class Method 
1. input/output이 없이 print만 하는 예시
    ```java
    class MyClass {
        static void sayHi() {
            System.out.println("Hi from MyClass");
        }
    }

    public class Main {
        public static void main(String[] args) {
            // Class Method는 그냥 {Class 이름}.{Class Method 이름}(); 처럼 호출할 수 있다. (선호)
            MyClass.sayHi();

            // new 키워드로 Instance를 생성한 다음에 호출할 수도 있다. (비선호)
            MyClass myclass1 = new MyClass();
            myclass1.sayHi();
        }
    }
    ```

2. input, output을 한개씩 받는 예시
    - input으로 시간 (int) 을 받고 output으로 input 시간에 해당되는 초 (int)를 내보내는 함수
    ```java
    class MyClass {
        static int getSeconds(int hours) {
            return hours * 60 * 60;
        }
    }

    public class Main {
        public static void main(String[] args) {
            int hours = 2;
            int converted_seconds = MyClass.getSeconds(hours);
            System.out.println(String.format("%d hours converted to %d seconds", hours, converted_seconds));
        }
    }
    ```
    - input으로 초 (int) 을 받고 output으로 input 시간에 해당되는 시간 (double)를 내보내는 함수
    ```java
    class MyClass {
        static double getHours(int seconds) {
            return seconds / 60.0 / 60.0;
        }
    }

    public class Main {
        public static void main(String[] args) {
            int seconds = 3141592;
            double converted_hours = MyClass.getHours(seconds);
            System.out.println(String.format("%d seconds converted to %f hours", seconds, converted_hours));
        }
    }
    ```
3. 여러개의 input 을 받는 예시
    - input으로 시간 (int)과 분(int)과 초(int) 받고 output으로 input 시간에 해당되는 초 (int)를 내보내는 함수
    ```java
    class MyClass {
        static int getSeconds(int hours, int minutes, int seconds) {
            return hours * 60 * 60 + minutes * 60 + seconds;
        }
    }

    public class Main {
        public static void main(String[] args) {
            int hours = 3;
            int minutes = 14;
            int seconds = 15;
            int converted_seconds = MyClass.getSeconds(hours, minutes, seconds);
            System.out.println(String.format("%d hour %d minute % second converted to %d seconds", hours, minutes, seconds, converted_seconds));
        }
    }
    ```
