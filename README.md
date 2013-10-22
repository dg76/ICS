ICS
===

Object-oriented php library for creating (and eventually reading) .ics iCal files

* This project does not yet support all functionality of the .ics format.

## Usage

	use Jsvrcek\ICS\Model\Calendar;
	use Jsvrcek\ICS\Model\CalendarEvent;
	
	use Jsvrcek\ICS\CalendarExport;
	
	$eventOne = new CalendarEvent();
	$eventOne->setStart(new \DateTime())
		->setSummary('Family reunion')
		->setUid('event-uid');
	
	$eventTwo = new CalendarEvent();
	$eventTwo->setStart(new \DateTime())
		->setSummary('Dentist Appointment')
		->setUid('event-uid');
	
	$calendar = new Calendar();
	$calendar->setProdId('-//My Company//Cool Calendar App//EN')
		->addEvent($eventOne)
		->addEvent($eventTwo);
	
	$calendarExport = new CalendarExport();
	$calendarExport->addCalendar($calendar);
	
	//output .ics formatted text
	echo $calendarExport->getStream();

## Todos

* Jsvrcek\ICS\Model\CalendarAlarm
* Jsvrcek\ICS\Model\CalendarTodo

## Reference
 
 * http://www.ietf.org/rfc/rfc2445.txt