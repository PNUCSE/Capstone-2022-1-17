# Capstone-2022-1-17

***
## 1. 프로젝트 소개

'포인트 클라우드를 이용한 3D 공간 생성/복원' 프로젝트입니다.<br/><br/>
Point Cloud는 LiDAR 센서를 사용하는 자율주행과, 건축물의 3 차원 가상 건설 환경 데이터인 BIM(Building Information Modeling)에서 활용됩니다. 해당 프로젝트에서는 집 내부에서 수집된 Point Cloud를 이용하여 3D 모델을 생성 및 복원하는 작업을 진행하였습니다.

#### 목표

- 포인트 클라우드 데이터로 표현되는 방 공간에서 천장, 벽, 바닥을 추출한다
- 방 공간 내부의 작은 물체 가구들을 분류하여 천장, 벽, 바닥과 가구를 분리한다
- 가구에 가려져 제거된 방의 영역을 복원하고 생성한 3D 공간에 텍스처를 입힌다
<br/><br/><br/>
***
## 2. 팀 소개

Ki Taeuk, ktw1421@naver.com, Reconstruction and Edit

Seo Juno, ocula5987@pusan.ac.kr, Visualization with Unity

Lee Haeseong, dlwlstjr@gmail.com, Algorithm Design and Implementation
<br/><br/><br/>
***
## 3. 시스템 구성도
![pipeline](https://user-images.githubusercontent.com/79833715/195857077-31bbe2da-45f3-46b3-9ac1-b18ac7e92ac5.png)
<br/><br/><br/>
***
## 4. 소개 및 시연 영상

<br/><br/><br/>
***
## 5. 설치 및 사용법

#### 프로젝트를 실행하기 위해 아래와 같은 라이브러리들이 필요합니다. 
1\) matplotlib
```
pip install matplotlib
```
2\) numpy
```
pip install numpy
```
3\) open3d
```
pip install open3d
```
4\) alphashape
```
pip install alphashape
```
<br/>

#### Input : main.py 파일의 37번 line의 메서드에 .ply 확장자를 가진 point cloud 데이터를 입력합니다.

```
pc = o3d.io.read_point_cloud("_________.ply")
```

<br/>

#### Output : mesh.obj라는 실내 공간 모델과 furniture.ply라는 분리된 가구 포인트 클라우드 데이터를 출력합니다.

```
o3d.io.write_point_cloud("furniture.ply", removed)
o3d.io.write_triangle_mesh("mesh.obj",mesh, print_progress=True)
```
