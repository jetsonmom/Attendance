# Attendance
# Face based attendance system using Nvidia Jetson nano 4GB
학교에서 제슨나노 출석부 만들어서 확인 해보고 싶었다.
자료를 못찾았는데 한글로 찾는게 아니라 영어로 찾았어야했던거다.
김종현 교수님이 몇개의 링크를 주셨다.
그런데 OPENCV버전 문제로 할 줄 몰라서 제타님께 도움을 청했다. 
그 후 성공을 했었고 다시 하는데 안되서 2일을 헤메다 구글 검색하고 드디어 해결해서 글을 남긴다.
내 힘으로 수정해서 해결하니 기뻣다.

#  이미지 굽기
이미지 JetsonNanoUb20 다운로드 후 zip 풀고 balenaetcher로 구워줌JetsonNanoUb20
1. Git clone and change directory
$ git clone https://github.com/VK-Ant/AttendanceSystem-JetsonAGX.git

$ jetson@nano:~/Downloads/AttendanceSystem-JetsonAGX$ pip show dlib   
   결과 WARNING: Package(s) not found: dlib

$ pip install dlib 
  결과
  Building wheels for collected packages: dlib
  Building wheel for dlib (PEP 517) ... -^canceled
$ pip install dlib -vvv 
결과 설치 성공 
[ 98%] Building CXX object CMakeFiles/_dlib_pybind11.dir/src/gui.cpp.o
  [100%] Linking CXX shared module /tmp/pip-install-wgljy5hq/dlib/build/lib.linux-aarch64-3.8/_dlib_pybind11.cpython-38-aarch64-linux-gnu.so
2. Install prerequisite library using requirement file
   $ pip3 install -r requirement.txt 
     결과 에러
      'The conflict is caused by:
	The user requested numpy==1.17.4
	opencv-python 4.5.2.54 depends on numpy>=1.19.3'
     requirment.txt 파일에서  numpy>=1.19.3로 수정하니 또 에러.  
     numpy>=1.18.5로 수정하니 넘어감
     또 다시 하니 에러 그래서 numpy>=1.19.2로 하니 넘어감![image](https://github.com/jetsonmom/Attendance/assets/92077615/bedc10fa-087a-4402-9f6e-542bae62212d)

  # 경로 조심 jetson@nano:~/Downloads/AttendanceSystem-JetsonAGX

  3. Take a picture of your input and save it to the “Attendance_data” folder
     $ python3 initial_data_capture.py  
       Please Enter your name:jetsonmom
     
5. Main script (Attendance system):
   $ python3 main.py
       23_08_13||15:22
       ['venkatesan.png', 'j.png', 'vk.png']
       ['venkatesan', 'j', 'vk']



