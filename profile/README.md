# FooBao-GIST
> **GIST 2023 2학기 - AI 실무프로젝트 TEAM B** <br/> **기간: 2023.09 ~ 2023.11**

## 팀 소개
김민준: 크롤링, 데이터 정리, 유사도 비교분석 결과 자료 생성

박재형: 크롤링, 데이터 정리, 메뉴판 OCR 전처리

양재원: 데이터 정리, 메뉴판 OCR 및 전처리

오세훈: 이미지 및 텍스트 유사도 비교 분석 / 발표자료 제작

이정환: 데이터 정리, 프로젝트 발표

최승훈: 데이터 정리, 이미지 및 텍스트 유사도 비교 분석, 결과 자료 생성

## 프로젝트 소개

프로젝트는 크게 

- 메뉴판 이미지와 리뷰 사진의 이미지를 비교하는 **ImageSimilarity** task
- 메뉴판 텍스트와 리뷰 사진의 이미지를 비교하는 **TextImageSimilarity** task

이렇게 두가지로 나누어 보실 수 있습니다.

**ImageSimilarity** task를 위해서는

1. 메뉴 이미지 및 텍스트, 리뷰 사진 Crawling
2. 리뷰사진 Food detection/crop 
3. CLIP cosine 유사도 측정

이렇게 세 과정을 거치고

**TextImageSimilarity** task를 위해서는

1. 리뷰 사진 Crawling
2. 메뉴판 OCR 전처리
3. 메뉴판 OCR
4. CLIP cosine 유사도 측정

이렇게 네 단계를 거치게 됩니다.

---

따라서

1. **FooBao-Crawling** repository로 
    
    메뉴 이미지, 메뉴 이름, 리뷰 사진을 Crawling하는 코드를 실행하여 주시고
    
2. **FooBao-ImageSimilarity** repository로 
    
    YOLOv5 food detection 학습 및 detect
    
    crop된 사진들을 crawling한 메뉴 이미지와 유사도 측정하여 최종 결과를 확인하시면 됩니다.
    

3. **FooBao-textOCR1** 에서는

   메뉴판에서 메뉴 텍스트만을 OCR하기 위한 전처리로 Yolov5로 학습된 detectNblur,

   그리고 Blur된 메뉴판에서 선명한 메뉴 텍스트를 pororo를 이용하여 OCR,

   마지막으로 txt로 저장된 메뉴 이름들로 description을 생성하여 CLIP에서 feature extraction 후 리뷰 사진들과 유사도 측정하여 최종 결과를 확인하시면 됩니다.

자세한 내용은 각 reposit의 readme를 다시 참조해주시길 바랍니다.
