[
    {
        "id": "f71aefae.228ba",
        "type": "tab",
        "label": "Flow 2"
    },
    {
        "id": "45170c00.6441b4",
        "type": "inject",
        "z": "f71aefae.228ba",
        "name": "",
        "topic": "",
        "payload": "",
        "payloadType": "date",
        "repeat": "5",
        "crontab": "",
        "once": true,
        "x": 110,
        "y": 100,
        "wires": [
            [
                "1397379d.8a3e58"
            ]
        ]
    },
    {
        "id": "1397379d.8a3e58",
        "type": "function",
        "z": "f71aefae.228ba",
        "name": "Payload",
        "func": "msg.headers={\n    deviceKey:\"NQfc1F4zrwhNhiP4\"\n    };\n\nreturn msg;",
        "outputs": 1,
        "noerr": 0,
        "x": 340,
        "y": 100,
        "wires": [
            [
                "be88fa0c.c56d18",
                "cf2b084d.e19758"
            ]
        ]
    },
    {
        "id": "aa9a5f1f.b2acc",
        "type": "debug",
        "z": "f71aefae.228ba",
        "name": "",
        "active": true,
        "console": "false",
        "complete": "payload",
        "x": 710,
        "y": 280,
        "wires": []
    },
    {
        "id": "be88fa0c.c56d18",
        "type": "http request",
        "z": "f71aefae.228ba",
        "name": "",
        "method": "GET",
        "ret": "txt",
        "url": "http://api.mediatek.com/mcs/v2/devices/DfhvgKzH/datachannels/Temperature/datapoints.csv",
        "tls": "",
        "x": 530,
        "y": 100,
        "wires": [
            [
                "aa9a5f1f.b2acc",
                "825bee70.ab06d"
            ]
        ]
    },
    {
        "id": "825bee70.ab06d",
        "type": "http response",
        "z": "f71aefae.228ba",
        "name": "",
        "statusCode": "",
        "headers": {},
        "x": 763,
        "y": 161,
        "wires": []
    },
    {
        "id": "cf2b084d.e19758",
        "type": "http request",
        "z": "f71aefae.228ba",
        "name": "",
        "method": "GET",
        "ret": "txt",
        "url": "http://api.mediatek.com/mcs/v2/devices/DfhvgKzH/datachannels/Humidity/datapoints.csv",
        "tls": "",
        "x": 515,
        "y": 191,
        "wires": [
            [
                "825bee70.ab06d",
                "aa9a5f1f.b2acc"
            ]
        ]
    }
]
