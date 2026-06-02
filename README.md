import streamlit as st

# 데이터 정의
popcorn_options = ['기본', '카라멜', '어니언']
drink_options = ['생수', '탄산음료']

st.title("🍿 CGV 부럽지 않은 팝콘 조합기")

# 1. 사용자가 직접 고르는 영역
st.header("1. 메뉴 직접 고르기")
user_popcorn = st.selectbox("팝콘을 고르세요", popcorn_options)
user_drink = st.radio("음료를 고르세요", drink_options)

st.info(f"👉 나의 선택: **{user_popcorn} 팝콘 + {user_drink}**")


st.markdown("---")


# 2. 질문하신 'for문 조합' 전체 출력 영역
st.header("2. 전체 세트메뉴 조합 (for문 결과)")

# 요청하신 이중 for문 그대로 스트림릿 화면에 출력합니다.
for popcorn in popcorn_options:
    for drink in drink_options:
        st.write(f"✅ 세트메뉴: {popcorn} 팝콘, {drink}")