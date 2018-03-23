# DANBEE.AI Documentaion
2018.03.16 기준
http://doc.danbee.ai

## Requirement
ruby 2.0 and above (전역 설치)

### window
 - https://rubyinstaller.org/downloads/
 - RubyInstallers download
 #### ruby 2.0.0 ~ 2.3.x
 1. run rubyinstaller.exe - "Add Ruby executables to your PATH" 반드시 체크 <br/>
 2. Development Kit download <br/> 
 3. Extract the compressed folder’s contents into any folder in C dirve <br/> 
 4. cd foldername <br/> 
 5. ruby dk.rb init <br/> 
 6. config.yml edit
  ```
  # 
  # Example:
  # ---
  # - C:/ruby19trunk
  # - C:/ruby192dev
  #
  --- 
  - C:\Ruby23-x64 #여기에 실제 Ruby를 설치한 위치를 입력해주세요.
  ```
 7. ruby dk.rb install <br/>
 #### ruby 2.4.x
  ruby installer download page 참고

## Install
git clone https://github.com/danbeeai/document.git <br/>
cd document <br/>
..document> gem install jekyll <br/>
..document> gem install bundler <br/>
..document> gem install wdm -v '0.1.1' <br/>
..document> bundle install <br/>

※ window 에서 SSL error 시 Gemfile 파일 내용중 source 를 https 에서 http 로 변경한후 다시 install <br/>

## START
..document> bundle exec jekyll serve

※ window 에서 Conversion error 시 cmd창에서, <br/>
  ..document> chcp 65001<br/>
위 명령어로 cmd utf-8로 encoding 후 serve 재실행 시도<br/>
  


## Manual Add/Edit
pages > danbeeDoc > md file edit

## Tutorial Add/Edit 
_posts > md file add/edit

## References
http://idratherbewriting.com/documentation-theme-jekyll/index.html



  
