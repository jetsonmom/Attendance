# Attendance
#Face based attendance system using Nvidia Jetson nano 4GB
학교에서 제슨나노 출석부 만들어서 확인 해보고 싶었다.
자료를 못찾았는데 한글로 찾는게 아니라 영어로 찾았어야했던거다.
김종현 교수님이 몇개의 링크를 주셨다.
그런데 OPENCV버전 문제로 할 줄 몰라서 제타님께 도움을 청했다. 
그 후 성공을 했었고 다시 하는데 안되서 2일을 헤메다 구글 검색하고 드디어 해결해서 글을 남긴다. 내 힘으로 수정해서 하니 기뻣다.


이미지 JetsonNanoUb20 다운로드 후 zip 풀고 balenaetcher로 구워줌JetsonNanoUb20

git clone https://github.com/VK-Ant/AttendanceSystem-JetsonAGX.git
dlib가 없어서 pep517에러가 나옴   jetson@nano:~/Downloads/AttendanceSystem-JetsonAGX$ pip show dlib   
WARNING: Package(s) not found: dlib

jetson@nano:~/Downloads/AttendanceSystem-JetsonAGX$ pip install dlib 했으나 역시 Building wheels for collected packages: dlib
  Building wheel for dlib (PEP 517) ... -^canceled
pip install dlib -vvv 명령 실행한 후  
드디어 설치 성공 
[ 98%] Building CXX object CMakeFiles/_dlib_pybind11.dir/src/gui.cpp.o
  [100%] Linking CXX shared module /tmp/pip-install-wgljy5hq/dlib/build/lib.linux-aarch64-3.8/_dlib_pybind11.cpython-38-aarch64-linux-gnu.so

  jetson@nano:~/Downloads/AttendanceSystem-JetsonAGX$ pip3 install -r requirement.txt 명령에서 다음과 같은 에러나옴 
  'The conflict is caused by:
	The user requested numpy==1.17.4
	opencv-python 4.5.2.54 depends on numpy>=1.19.3
'
requirment.txt 파일에서  numpy>=1.19.3로 수정하니 또 에러가 남 그래서 메시지대로 1.8.15로 수정하니 넘어감

jetson@nano:~/Downloads/AttendanceSystem-JetsonAGX$ python3 initial_data_capture.py
Please Enter your name:j
jetson@nano:~/Downloads/AttendanceSystem-JetsonAGX$ python3 main.py
23_08_13||15:22
['venkatesan.png', 'j.png', 'vk.png']
['venkatesan', 'j', 'vk']



