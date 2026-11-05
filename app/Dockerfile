# 1) 베이스 이미지: 공식 nginx (alpine = 경량 리눅스)
FROM nginx:alpine

# 2) 이미지 정보(메타데이터)
LABEL org.opencontainers.image.title="codyssey-web"
LABEL org.opencontainers.image.description="Codyssey workstation custom nginx"

# 3) 환경 변수
ENV APP_ENV=dev

# 4) 내 정적 페이지로 교체
COPY site/ /usr/share/nginx/html/

# 5) 컨테이너가 사용하는 포트 문서화
EXPOSE 80

# 6) 헬스체크: 웹 서버가 응답하는지 주기적으로 확인
HEALTHCHECK --interval=30s --timeout=3s CMD wget -qO- http://localhost/ > /dev/null || exit 1
