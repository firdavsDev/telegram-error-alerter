==============================================================
Handle errors and send it Telegram group!
==============================================================

import Alerter

tg_alert = Alerter(bot_token='YOUR_BOT_TOKEN', chat_id='YOUR_CHAT_ID')
#or
tg_alert = Alerter.from_environment() #Recommend

method_1: tg_alert.send_message(chat_id=111222333, text='Message text')
#or
method_2: as decorator
@tg_alert
def some_func_that_can_raise_an_exception():
raise RuntimeError('this is an exception')

We could use in except scope as:
        except Exception as e:
            return tg_alert.custom_alert(text=e)

