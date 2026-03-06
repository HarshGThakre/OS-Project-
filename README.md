# python-alarm-clock-
Import datetime
import time

def set_alarm():
    print("--- Python Alarm Clock ---")
    alarm_time = input("Enter alarm time (HH:MM:SS): ")
    
    while True:
        # Get the current time in the same format
        now = datetime.datetime.now().strftime("%H:%M:%S")
        
        if now == alarm_time:
            print("\n⏰ WAKE UP! ⏰")
            handle_snooze()
            break
            
        # Wait 1 second before checking again to save CPU
        time.sleep(1)

def handle_snooze():
    choice = input("Press 's' to snooze (5 mins) or 'q' to quit: ").lower()
    
    if choice == 's':
        snooze_time = 5 
        print(f"Snoozing for {snooze_time} minutes...")
        time.sleep(snooze_time * 60)
        print("\n⏰ WAKE UP AGAIN! ⏰")
        handle_snooze() # Recursive call for repeated snoozing
    else:
        print("Alarm deactivated. Have a great day!")

if __name__ == "__main__":
    set_alarm()
    
