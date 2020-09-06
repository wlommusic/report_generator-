# this are all the necessary functions needed for our code to work this will generate no output.
def get_event_date(event):
  return event.date

def current_users(events):
  events.sort(key=get_event_date)
  machines = {}
  for event in events:
    if event.machine not in machines:
      machines[event.machine] = set()
    if event.type == "login":
      machines[event.machine].add(event.user)
    elif event.type == "logout":
      machines[event.machine].remove(event.user)
  return machines

def generate_report(machines):
  for machine, users in machines.items():
    if len(users) > 0:
      user_list = ", ".join(users)
      print("{}: {}".format(machine, user_list))
      
#creating a event class.
class Event:
  def __init__(self, event_date, event_type, machine_name, user):
    self.date = event_date
    self.type = event_type
    self.machine = machine_name
    self.user = user

# now to see if it runs create a list contaaining all the events
events = [
    Event('2020-01-21 12:45:56', 'login', 'myworkstation.local', 'shivam'),
    Event('2020-01-22 15:53:42', 'logout', 'webserver.local', 'harsh'),
    Event('2020-01-21 18:53:21', 'login', 'webserver.local', 'dipta'),
    Event('2020-01-22 10:25:34', 'logout', 'myworkstation.local', 'shivam'),
    Event('2020-01-21 08:20:01', 'login', 'webserver.local', 'harsh'),
]

# now feed the list to the current_users function
users = current_users(events)
print(users)

#run this code to generate the report
generate_report(users)
