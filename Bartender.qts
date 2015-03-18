var stateM1 = { ind: false};
var stateM2 = { ind: false};
var stateM3 = { ind: false};
var stateM4 = { ind: false};

var disp = brick.display();
var buttons = brick.keys();

var motor1 = brick.motor("M1");
var motor2 = brick.motor("M2");
var motor3 = brick.motor("M3");
var motor4 = brick.motor("M4");

var strArray = ["Привет",
"Как жизнь",
"ТРИК победит всех",
"Свободу попугаям",
"Заходи ещё"];

var bye = "Пока";

disp.addLabel("Bartender", 160, 120);

function turnOff() {
	stateM1.ind = false;
	stateM2.ind = false;
	stateM3.ind = false;
	stateM4.ind = false;
	motor1.powerOff();
	motor2.powerOff();
	motor3.powerOff();
	motor4.powerOff();
}

function checkAndChange (st, m) {
	if (st.ind == false) {
		st.ind = true;
		m.setPower(100);
	} else {
		st.ind = false;
		m.powerOff();
	}
}

function getRandomInt() {
	return Math.floor(Math.random() * (strArray.length));
}

buttons.buttonPressed.connect(
	function (code, state) {
		if (state == 0) {
			switch (code) {
				case KeysEnum.Down: {
					checkAndChange(stateM1, motor1);
					brick.say(strArray[getRandomInt()]);
					break;
				}

				case KeysEnum.Up: {
					checkAndChange(stateM2, motor2);
					brick.say(strArray[getRandomInt()]);
					break;
				}

				case KeysEnum.Left: {
					checkAndChange(stateM3, motor3);
					brick.say(strArray[getRandomInt()]);
					break;
				}

				case KeysEnum.Right: {
					checkAndChange(stateM4, motor4);
					brick.say(strArray[getRandomInt()]);
					break;
				}

				case KeysEnum.Enter: {
					turnOff();
					brick.say(bye);
					break;
				}
			}
		}
	}
)

brick.run();
