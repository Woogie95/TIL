### System.in

- 사용자의 키보드 입력은 System.in 을 통해 얻을 수 있다.  System.in 은 키보드로 얻는 InputStream 인데 `InputStream은 입력을 byte 단위로 읽어들인다.` 하지만 byte 단위로 읽으면 사람이 읽기에는 좀 불편한 문자들이 출력된다. 그래서 생겨난 것이 `InputStreamReader`이다.
- `InputStreamReader는 입력을 character 로 읽어들인다.` 키보드로 입력하는 글자 한개에 해당된다고 할 수 있다. 하지만 한 글자가 아닌 `줄단위의 문자열을 입력으로 받으려면 마찬가지로 불편하다. 그래서 생겨난 것이 BufferedReader`이다.
- BufferedReader는 `InputStreamReader에 버퍼링 기능을 추가한 것`으로 데이터를 사용자가 요청할때마다 매번 읽어오기 보다는 일정량사이즈로 한번에 읽어온 후 버퍼에 보관한다. 그리고 사용자가 요구할 때 버퍼에서 읽어오게 한다. 결국, `BufferedReader를 이용하면 속도를 향상시키고 시간의 부하를 줄일수 있게 된다.`
- BufferedReader의 readLine이라는 메소드를 이용하면 줄단위로 사용자의 입력을 읽어들일 수 있다.

<출력 타입>
- InputStream : byte
- InputStreamReader : character
- BufferedReader : 문자열

### InputStreamReader

- `byte stream 에서 문자 stream 까지의 다리`
- byte 를 읽고 지정된 문자 집합을 사용하여 문자로 디코딩
- InputStreamReader 의 read() 메소드 중 하나를 호출할 때마다 기본 byte input stream 에서 하나 이상의 byte 가 읽힐 수 있음
- byte 를 문자로의 효율적인 변환을 위해, 현재 읽기 작업을 만족시키기 위해 필요한 것보다 더 많은 byte 를 기본 스트림에서 미리 읽을 수 있음
- `BufferedReader 를 최고의 효율로 사용하기 위해 InputStreamReader 를 포함`

### BufferedReader

- 문자 입력 스트림에서 텍스트를 읽고 문자를 버퍼링하여 문자, 배열 및 행을 효율적으로 읽을 수 있도록 함
- 버퍼 크기 지정 가능, default 크기로 대부분의 용도로 사용 가능함
