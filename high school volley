import streamlit as st
import json

# ฐานข้อมูลทีมวอลเลย์บอล
# เราจะเก็บข้อมูลไว้ในตัวแปร Python Dictionary
DATABASE = {
    "teams": [
        {
            "name": "Black Crow",
            "school": "Karasuno High",
            "players": [
                {
                    "name": "Shoyo",
                    "position": "Middle Blocker",
                    "jersey_number": 10,
                    "attributes": {
                        "jumping_power": 95,
                        "speed": 90,
                        "spiking": 75,
                        "blocking": 60,
                        "reception": 50,
                        "serving": 65,
                        "stamina": 85
                    }
                },
                {
                    "name": "Kageyama",
                    "position": "Setter",
                    "jersey_number": 9,
                    "attributes": {
                        "jumping_power": 80,
                        "speed": 85,
                        "spiking": 80,
                        "blocking": 70,
                        "reception": 75,
                        "serving": 90,
                        "stamina": 90
                    }
                },
                {
                    "name": "Nishinoya",
                    "position": "Libero",
                    "jersey_number": 4,
                    "attributes": {
                        "jumping_power": 65,
                        "speed": 95,
                        "spiking": 20,
                        "blocking": 10,
                        "reception": 95,
                        "serving": 70,
                        "stamina": 90
                    }
                },
                {
                    "name": "Azumane",
                    "position": "Outside Hitter",
                    "jersey_number": 3,
                    "attributes": {
                        "jumping_power": 88,
                        "speed": 70,
                        "spiking": 95,
                        "blocking": 80,
                        "reception": 60,
                        "serving": 85,
                        "stamina": 80
                    }
                },
                {
                    "name": "Tsukishima",
                    "position": "Middle Blocker",
                    "jersey_number": 11,
                    "attributes": {
                        "jumping_power": 75,
                        "speed": 65,
                        "spiking": 70,
                        "blocking": 90,
                        "reception": 60,
                        "serving": 70,
                        "stamina": 80
                    }
                }
            ]
        },
        {
            "name": "Red Lion",
            "school": "Shiratorizawa High",
            "players": [
                {
                    "name": "Ushijima",
                    "position": "Outside Hitter",
                    "jersey_number": 1,
                    "attributes": {
                        "jumping_power": 90,
                        "speed": 80,
                        "spiking": 98,
                        "blocking": 85,
                        "reception": 75,
                        "serving": 95,
                        "stamina": 95
                    }
                },
                {
                    "name": "Shirabu",
                    "position": "Setter",
                    "jersey_number": 10,
                    "attributes": {
                        "jumping_power": 70,
                        "speed": 75,
                        "spiking": 60,
                        "blocking": 65,
                        "reception": 80,
                        "serving": 70,
                        "stamina": 85
                    }
                },
                {
                    "name": "Goshiki",
                    "position": "Outside Hitter",
                    "jersey_number": 8,
                    "attributes": {
                        "jumping_power": 85,
                        "speed": 85,
                        "spiking": 90,
                        "blocking": 75,
                        "reception": 65,
                        "serving": 80,
                        "stamina": 85
                    }
                }
            ]
        }
    ]
}

# ส่วนนี้คือ UI ของ Streamlit
st.set_page_config(layout="wide")
st.title("🏐 Volleyball Manager: Team Database")
st.subheader("ฐานข้อมูลทีมและผู้เล่น")

# สร้าง list ของชื่อทีมเพื่อใช้ใน selectbox
team_names = [team['name'] for team in DATABASE['teams']]

# ให้ผู้ใช้เลือกทีมจาก dropdown
selected_team_name = st.selectbox("เลือกทีมที่คุณต้องการดูข้อมูล", team_names)

# ค้นหาข้อมูลทีมที่ถูกเลือก
selected_team = next((team for team in DATABASE['teams'] if team['name'] == selected_team_name), None)

if selected_team:
    st.markdown(f"### ทีม: **{selected_team['name']}** ({selected_team['school']})")
    
    st.write("---")
    st.subheader("รายชื่อผู้เล่น")

    # แบ่งหน้าจอเป็น 3 คอลัมน์เพื่อแสดงผลผู้เล่น
    cols = st.columns(3)
    
    for i, player in enumerate(selected_team['players']):
        with cols[i % 3]:
            # ใช้ st.expander เพื่อซ่อน/เปิดดูค่าพลัง
            with st.expander(f"**{player['name']}** - #{player['jersey_number']} ({player['position']})"):
                st.write("---")
                # แสดงค่าพลังของผู้เล่น
                for attr, value in player['attributes'].items():
                    st.text(f"- {attr.replace('_', ' ').title()}: {value}")
