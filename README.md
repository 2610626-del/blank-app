import streamlit as st

# 1. 옵션 데이터 정의
popcorn_options = ['기본', '카라멜', '어니언']
drink_options = ['생수', '탄산음료']

# 2. 앱 타이틀 및 설명
st.title("🎬 영화관 세트메뉴 고르기")
st.write("원하는 팝콘과 음료를 선택해 주세요!")

st.divider() # 구분선

# 3. 레이아웃 나누기 (왼쪽: 선택 사이드, 오른쪽: 결과 사이드)
col1, col2 = st.columns(2)

with col1:
    st.subheader("🛒 메뉴 선택")
    # 라디오 버튼이나 셀렉트박스로 선택 가능
    selected_popcorn = st.selectbox("🍿 팝콘 종류", popcorn_options)
    selected_drink = st.radio("🥤 음료 종류", drink_options)

with col2:
    st.subheader("📋 선택한 메뉴")
    st.write(f"**🍿 팝콘:** {selected_popcorn} 팝콘")
    st.write(f"**🥤 음료:** {selected_drink}")
    
    st.write("") # 공백 추가
    
    # 버튼 클릭 시 최종 선택 메뉴 출력
    if st.button("🛍️ 주문 담기"):
        st.success(f"**세트메뉴: {selected_popcorn} 팝콘, {selected_drink}** 주문이 완료되었습니다!")

st.divider()

# 4. 보너스: 기존 코드처럼 모든 가능한 조합 보기 (접고 펼치기 기능)
with st.expander("👀 가능한 모든 세트메뉴 조합 확인하기"):
    st.write("현재 제공되는 전체 세트메뉴 리스트입니다.")
    for popcorn in popcorn_options:
        for drink in drink_options:
            st.write(f"• 세트메뉴: {popcorn} 팝콘, {drink}")