# ◼️ cookping 
항해99 9기 C반 11조 미니프로젝트
2022.09.19 - 2022.09.22 

## ◼️ 팀원 👨‍👧‍👦
권순한(팀장), 장윤서, 주재정

## ◼️ 프로젝트 소개 👩‍🏫
굽기만 하는 요리에 지쳤어요...!😖 
캠핑가서 다른 사람들은 멋있고 다양한 요리 하던데 어떻게 하는지 모르겠어요 😓
캠핑 요리 고수입니다!🧐 알고 있는 정보를 공유하고 싶어요 😎
쿡핑은 다양한 캠핑 요리 레시피를 손쉽게 공유하고 찾아볼 수 있는 사이트 입니다.
Youtube 링크를 공유해 보세요! 🎬

## ◼️ 프로젝트 주소 📍
[COOKPING] http://shoumini.shop/

## ◼️ 프로젝트 S.A ✏️
https://hightechsoon.tistory.com/15

## ◼️ 프로젝트 시연 영상 🎬
https://youtu.be/JW8gVQv8Umo


## ◼️ 기술스택 🔨
HTML / CSS / JavaScript / Python / Flask / mongoDB / Jinja2 /JQuery / Linux / AWS 

## ◼️ API Table ✏️
기능 | Method | URL | Request | response | 
--- | --- | --- | --- |--- |
로그인 페이지 로드 | POST | /login | -- | return render_template('index.html', user_info=user_info) |
회원가입 페이지 로드 | POST | /login | -- | return render_template('index.html', user_info=user_info) |
로그인 | POST | /sign_in |{'username': username_receive, 'password': pw_hash} |로그인 성공 - return jsonify({'result': 'success', 'token': token}) 로그인 실패 - return jsonify({'result': 'fail', 'msg': '아이디/비밀번호가 일치하지 않습니다.'}) |
회원가입 | POST | /sign_up/save | {"username": username_receive, "password": password_hash, "profile_name": username_receive, "profile_pic": "", "profile_pic_real": "profile_pics/profile_placeholder.png", "profile_info": "" } | return render_template('index.html', user_info=user_info) |
중복 검사 | POST | /login | "username": username_receive | return jsonify({'result': 'success', 'exists': exists})|
메인페이지 | GET | /get_posts | /get_posts | return jsonify({"result": "success", "msg": "포스팅을 가져왔습니다.","posts":posts}) |
글쓰기 | POST | /posting | "username": user_info["username"], "profile_name": user_info["profile_name"], "profile_pic_real": user_info["profile_pic_real"], "comment": comment_receive, "date": date_receive | return jsonify({"result": "success", 'msg': '포스팅 성공'}) |
포스팅 | GET | /sign_up/check_dup | post["_id"] = str(post["_id"]) | return jsonify({"result": "success", "msg": "포스팅을 가져왔습니다.","posts":posts}) |

## ◼️ 구현 기능 
### 1.Login Page 로그인
<img width="1440" alt="KakaoTalk_20220922_162812239_01" src="https://user-images.githubusercontent.com/99253403/191685729-bfda3675-baa6-47f2-a2ab-7e2e1ffac3df.png">
JWT 방식으로 구현
회원가입 버튼 클릭 시 회원 가입페이지로 이동

### 2.Register Page 회원가입
<img width="1440" alt="KakaoTalk_20220922_162812239_03" src="https://user-images.githubusercontent.com/99253403/191685755-b60cf178-b00b-455a-9172-f1f32ebee894.png">
아이디 중복확인 시 중복아이디 및 아이디 유무 체크
비밀번호 입력칸과 재입력칸의 비밀번호 일치여부 체크

### 3. Main Page 메인화면
<img width="1440" alt="KakaoTalk_20220922_162812239_02" src="https://user-images.githubusercontent.com/99253403/191685937-7c9d4da4-a726-4d3b-acbb-307f12e77856.png">
<img width="1440" alt="KakaoTalk_20220922_162812239_04" src="https://user-images.githubusercontent.com/99253403/191685845-3cfe57d0-47e6-4e03-a3f0-a919edb6d8ee.png">
User들이 작성한 글들을 보여주는 페이지
토글아이콘 클릭시 내비게이션 나타남 (모바일 또는 화면 사이즈 작을 경우)
내비게이션 바의 로그아웃 버튼 클릭 시 로그인페이지로 이동 
내비게이션 바에서 텍스트 클릭시 해당 페이지로 이동 (소개페이지)
글쓰기 화면에서 생성한 게시물이 화면에 나타남

### 4. Posting Page 글쓰기 화면
<img width="1440" alt="KakaoTalk_20220922_162812239" src="https://user-images.githubusercontent.com/99253403/191685865-29ed362d-cbfb-4f91-8b82-97bef94df8b0.png">
글제목, 코멘트, URL 을 작성할 수 있는 입력란 
유튜브 URL 작성 시, 해당 유튜브영상의 썸네일과 링크가 
메인페이지에 나타남
작성 버튼 클릭시, DB에 해당 글이 저장

### 5.About Page 소개 화면
![Screenshot 2022-09-22 at 16 34 25](https://user-images.githubusercontent.com/99253403/191686118-e38856a1-d15f-4640-885c-4ff8e8230041.JPG)

쿡핑과 팀원의 소개를 보여주는 페이지 
보러가기 아이콘 클릭시 메인페이지로 이동


