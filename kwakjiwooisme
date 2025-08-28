import streamlit as st
import datetime
import random

# 운세 메시지 데이터
fortunes = [
    "오늘은 당신이 계획한 일이 술술 풀리는 날입니다. 자신감을 가지고 도전하세요!",
    "작은 행운이 당신을 찾아올 거예요. 주변을 잘 살펴보세요.",
    "오늘은 새로운 사람을 만나거나 뜻밖의 기회를 얻을 수 있는 날입니다. 열린 마음으로 하루를 보내세요.",
    "잠시 멈춰서 자신을 돌아보는 시간을 가져보세요. 내면의 평화를 찾을 수 있습니다.",
    "오늘은 재물운이 좋은 날입니다. 예상치 못한 수입이 생길 수도 있어요.",
    "사람들과의 관계에서 기쁨을 느낄 수 있는 하루입니다. 먼저 다가가서 대화를 시도해 보세요.",
    "건강을 챙기기에 좋은 날입니다. 가벼운 운동이나 산책을 즐겨보세요.",
    "오늘은 창의력이 샘솟는 날이에요. 새로운 아이디어를 정리하거나 취미 생활에 몰두해 보세요.",
]

# 오늘의 운세 가져오는 함수
def get_daily_fortune(birth_date):
    """
    생년월일을 기반으로 오늘의 운세 메시지를 가져옵니다.
    실제 운세 로직이 아닌, 임의의 메시지를 반환합니다.
    """
    # 생년월일과 오늘의 날짜를 이용해 고정된 난수 시드를 생성
    seed_value = birth_date.strftime("%Y%m%d") + datetime.date.today().strftime("%Y%m%d")
    random.seed(int(seed_value))
    
    # 리스트에서 임의의 운세 메시지를 선택
    fortune_message = random.choice(fortunes)
    
    return fortune_message

# Streamlit 앱의 메인 함수
def main():
    st.set_page_config(page_title="오늘의 운세", layout="centered")

    st.title("🔮 오늘의 운세")
    st.write("생년월일을 입력하면 오늘의 운세를 알려드립니다.")

    # 생년월일 입력 위젯
    birth_date = st.date_input(
        "생년월일을 선택해주세요",
        datetime.date(1990, 1, 1), # 기본값 설정
        max_value=datetime.date.today()
    )

    # 운세 보기 버튼
    if st.button("운세 보기"):
        # 운세 함수 호출
        fortune_message = get_daily_fortune(birth_date)

        st.subheader(f"{birth_date.strftime('%Y년 %m월 %d일')} 오늘의 운세")
        st.info(fortune_message)

if __name__ == "__main__":
    main()
