# DANBEE.AI Documentaion
2017.10.10 기준
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
 6. ruby dk.rb install <br/>
 #### ruby 2.4.x
  ruby installer download page 참고

## Install
git clone https://github.com/danbeeai/document.git <br/>
cd document <br/>
..document> gem install jekyll <br/>
..document> gem install bundler <br/>
..document> bundle install <br/>

## START
..document> bundle exec jekyll serve

※ window 에서 Conversion error 시 cmd창에서, <br/><br/>
  ..document> chcp 65001<br/><br/>
  - 위 명령어로 cmd utf-8로 encoding 후 serve 재실행 시도<br/>
  


## Manual Add/Edit
pages > danbeeDoc > md file edit

## Tutorial Add/Edit 
_posts > md file add/edit



  
