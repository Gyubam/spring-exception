# 스프링 예외 처리 코드 구현

### servlet 통한 예외 처리
- filter
- interceptor

#### 요청 흐름 (error-ex 요청)
1. WAS(/error-ex, dispatchType=REQUEST) -> 필터 -> 서블릿 -> 인터셉터 -> 컨트롤러
2. WAS(여기까지 전파) <- 필터 <- 서블릿 <- 인터셉터 <- 컨트롤러(예외발생)
3. WAS 오류 페이지 확인
4. WAS(/error-page/500, dispatchType=ERROR) -> 필터(x) -> 서블릿 -> 인터셉터(x) -> 
컨트롤러(/error-page/500) -> View

### BasicErrorController 통한 예외 처리
- 뷰 템플릿 생성 후 자동 적용

