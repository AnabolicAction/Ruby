# ruby 챗봇만들기

rb.likelion.io에서 챗봇만들기



### 1.안녕

~~~ruby
puts "안녕하세요"
~~~

#### 2.코스피

~~~ruby
require 'httparty'
require 'nokogiri'
#원하는 정보가 있는 주소로 접근
url='http://finance.naver.com/sise/'
#요청을 보내고 응답을 저장
res = HTTParty.get(url)
#조작하기 편하게 바꾸기
data=Nokogiri::HTML(res.body)
#바꾼 정보중 원하는 정보만 뽑아서
customData =data.css("#KOSPI_now").text
#출력
puts customData
~~~

#### 3.로또

~~~ruby
#lotto = Array(1..45).sample(6).sort 밑에랑 똑같다!
lotto=(1...45).to_a.sample(6).sort.to_s
puts lotto
~~~

