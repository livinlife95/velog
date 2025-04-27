<p>컴퓨터 프로그램 작동과정</p>
<blockquote>
<p>코드를 빌드(코드 파일을 exe파일로 변환) &gt;&gt; 운영체제 (하드 --&gt; 메모리 --&gt; cpu) 거쳐서 출력장치로</p>
</blockquote>
<p>메모리 레이아웃 (낮은 주소부터)</p>
<pre><code class="language-sql">|----------------------|
|      Text 영역       |  ← 코드 (명령어)
|----------------------|
|      Data 영역       |  ← 전역 변수, static 변수
|----------------------|
|     BSS 영역         |  ← 초기화되지 않은 전역/정적 변수
|----------------------|
|      Heap 영역       |  ← 동적 메모리 (malloc, new 등)
|----------------------|
|      Stack 영역      |  ← 함수 호출, 지역 변수
|----------------------|
</code></pre>
<ol>
<li>Text 영역</li>
</ol>
<p>실행할 코드(기계어 명령어)가 저장되는 공간</p>
<p>읽기 전용 (수정 금지), 공유 가능 (같은 프로그램 여러 개 돌릴 때 메모리 절약)</p>
<ol start="2">
<li>Data 영역</li>
</ol>
<p>초기값이 있는 전역 변수와 static 변수가 저장됨</p>
<p>프로그램이 시작될 때 운영체제가 이 값을 메모리에 로딩</p>
<ol start="3">
<li>BSS 영역</li>
</ol>
<p>초기화되지 않은 전역 변수와 static 변수가 저장됨</p>
<p>실행 전에 0으로 자동 초기화됨</p>
<p>예: static int count; (초기값 X)</p>
<ol start="4">
<li>Heap 영역</li>
</ol>
<p>프로그램 실행 중 동적으로 할당되는 메모리 (예: C에서 malloc, C++의 new)</p>
<p>직접 할당/해제 필요</p>
<p>위로(고주소 방향) 확장</p>
<ol start="5">
<li>Stack 영역</li>
</ol>
<p>함수 호출 시 생기는 지역 변수, 매개변수, 리턴 주소 등을 저장</p>
<p>함수가 끝나면 자동 해제</p>
<p>아래로(저주소 방향) 확장</p>
<p>Stack Overflow는 여기서 이름이 유래됨</p>
<hr />
<p>[1] HelloWorld</p>
<pre><code class="language-cpp">#include &lt;iostream&gt; // iostream이라는 헤더를 포함(include)

using namespace std; // 네임스페이스 설명 std::cout

int main() // entry point
{
    // 주석(comment) 다는 방법

    cout &lt;&lt; &quot;Hello, World!&quot; &lt;&lt; endl;
    // printf(&quot;Hello World!!! by printf&quot;);

    return 0;
}
</code></pre>
<p>[2] 자료형</p>
<pre><code class="language-cpp"></code></pre>
<pre><code class="language-markdown">| 자료형       | 크기 (byte) | 비고 |
|--------------|-------------|------|
| `char`       | 1 byte      | 문자 하나 (ASCII), 부호 있음 (`signed char`) 또는 없음 (`unsigned char`) |
| `bool`       | 1 byte      | true / false |
| `short`      | 2 bytes     | `short int`와 같음 |
| `int`        | 4 bytes     | 기본 정수형 |
| `long`       | 4 bytes     | 일부 시스템에서는 8 bytes |
| `long long`  | 8 bytes     | 아주 큰 정수 |
| `float`      | 4 bytes     | 단정도 실수 |
| `double`     | 8 bytes     | 배정도 실수 |
| `long double`| 8~16 bytes  | 시스템에 따라 다름 |

</code></pre>