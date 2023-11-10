Разработать полную ERD домена.

Диаграма в Markup

```xml

Patient {
	id integer pk increments
	typePolicy text
	numberPolicy integer
	Surename text
	GivenNames text
	DateOfBirth date
	sex binary
	hillHistoryId integer > healthHistory.id
}

healthHistory {
	id integer pk increments
	AnalysesId integer > Analysis.id
	DiagnosId string > ICD-10.idICD
}

Doctor {
	id integer pk increments
	Surename text
	GivenNames text
	DateOfBirth datetime
	Speciality string
	scheduleDoctorId integer > undefined.undefined
}

Schedule {
	id integer pk increments
	idPatient integer *> Patient.id
	idDoctor integer *> Doctor.id
	appointment datetime
	cabinet integer
	comments text
}

ICD-10 {
	idICD string pk unique
	nameICD string unique
	description text
}

Analysis {
	id integer pk increments
	idPatient integer *> Patient.id
	dateOfAnalysis date
	typeOfAnalysis string
	AnalysisConclusion text
}

Procedure {
	id integer pk increments
	idPatient integer > Patient.id
	idStaff integer > Staff.id
	datetime datetime
	typeOfProcedure text
}

Staff {
	id integer pk increments
	Surename text
	GivenNames text
	dateOfBirth datetime
	job integer
}

```
