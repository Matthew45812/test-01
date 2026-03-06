# test-01
此遊戲為AI(Gemini)生成，運行於VS Code的猜數字遊戲，遊戲名稱為:數字大冒險
遊戲說明:這是一款考驗邏輯與直覺的經典猜謎遊戲。魔王在心裡想了一個神祕數字，你必須在有限的資源內找出真相！
遊戲規則:
數字範圍：謎底介於 1 到 100 之間（包含 1 與 100）。
挑戰次數：你總共有 7 次 猜測機會。
線索回饋：
*若猜得太高，系統會提示 🔽 太大了。
*若猜得太低，系統會提示 🔼 太小了。
勝利條件：在次數用完前精準命中目標數字。

##以下為程式碼
import random

def start_game():
    print("=" * 30)
    print("  🎮 歡迎來到數字大冒險！ 🎮")
    print("=" * 30)
    print("我心裡想了一個 1 到 100 之間的數字。")
    print("你有 7 次機會來挑戰我！\n")

    # 產生隨機解答
    answer = random.randint(1, 100)
    attempts = 0
    max_attempts = 7

    while attempts < max_attempts:
        try:
            # 讓玩家輸入數字
            guess = int(input(f"第 {attempts + 1} 次嘗試 - 請輸入數字: "))
        except ValueError:
            print("❌ 哎呀！這不是數字，請重新輸入。")
            continue

        attempts += 1

        if guess < answer:
            print("🔼 太小了！往大一點猜。")
        elif guess > answer:
            print("🔽 太大了！往小一點猜。")
        else:
            print(f"\n🎉 太強了！你竟然只用了 {attempts} 次就猜中了！")
            break
        
        # 剩餘次數提示
        if attempts < max_attempts:
            print(f"剩餘次數：{max_attempts - attempts}\n")
        else:
            print(f"\n👻 殘念！機會用完了。正確答案是 {answer}。")

    print("\n遊戲結束，感謝遊玩！")

if __name__ == "__main__":
    start_game()
