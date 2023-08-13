# Attendance
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



