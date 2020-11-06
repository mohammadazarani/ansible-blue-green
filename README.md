Mohammad Abdollahzade
==================

Quick note
----------
I start this porject on friday, at 9:00 AM and finish the main part at 5:00 PM

I test it on my local, actually my laptop isn't good enough to create 3 nodes




project structure
-----------------

ansible-blue-green/
├── ansible.cfg
├── apps
│   ├── v1.0.0
│   │   ├── Dockerfile
│   │   ├── go.mod
│   │   ├── go.sum
│   │   └── main.go
│   ├── v2.0.0
│   │   ├── Dockerfile
│   │   ├── go.mod
│   │   ├── go.sum
│   │   └── main.go
│   ├── v3.0.0
│   │   ├── Dockerfile
│   │   ├── go.mod
│   │   ├── go.sum
│   │   └── main.go
│   └── v4.0.0
│       ├── Dockerfile
│       ├── go.mod
│       ├── go.sum
│       └── main.go
├── blue-green
│   ├── defaults
│   │   └── main.yml
│   ├── files
│   ├── handlers
│   │   └── main.yml
│   ├── meta
│   │   └── main.yml
│   ├── README.md
│   ├── tasks
│   │   ├── main.yml
│   │   └── v2.yml
│   ├── templates
│   │   └── nginx.conf.j2
│   ├── tests
│   │   ├── inventory
│   │   └── test.yml
│   └── vars
│       └── main.yml
├── blue-green-v2
│   ├── defaults
│   │   └── main.yml
│   ├── files
│   ├── handlers
│   │   └── main.yml
│   ├── meta
│   │   └── main.yml
│   ├── README.md
│   ├── tasks
│   │   ├── main.yml
│   │   └── v3.yml
│   ├── templates
│   │   └── nginx.conf.j2
│   ├── tests
│   │   ├── inventory
│   │   └── test.yml
│   └── vars
│       └── main.yml
├── blue-green-v3
│   ├── defaults
│   │   └── main.yml
│   ├── files
│   ├── handlers
│   │   └── main.yml
│   ├── meta
│   │   └── main.yml
│   ├── README.md
│   ├── tasks
│   │   ├── main.yml
│   │   └── v4.yml
│   ├── templates
│   │   └── nginx.conf.j2
│   ├── tests
│   │   ├── inventory
│   │   └── test.yml
│   └── vars
│       └── main.yml
├── build
│   ├── defaults
│   │   └── main.yml
│   ├── files
│   ├── handlers
│   │   └── main.yml
│   ├── meta
│   │   └── main.yml
│   ├── README.md
│   ├── tasks
│   │   ├── go.yml
│   │   └── main.yml
│   ├── templates
│   ├── tests
│   │   ├── inventory
│   │   └── test.yml
│   └── vars
│       └── main.yml
├── docker
│   ├── defaults
│   │   └── main.yml
│   ├── files
│   ├── handlers
│   │   └── main.yml
│   ├── meta
│   │   └── main.yml
│   ├── README.md
│   ├── tasks
│   │   ├── main.yml
│   │   └── ubuntu.yml
│   ├── templates
│   ├── tests
│   │   ├── inventory
│   │   └── test.yml
│   └── vars
│       └── main.yml
├── first_run.txt
├── inventory
├── main.yml
├── nginx
│   ├── defaults
│   │   └── main.yml
│   ├── files
│   ├── handlers
│   │   └── main.yml
│   ├── meta
│   │   └── main.yml
│   ├── README.md
│   ├── tasks
│   │   ├── main.yml
│   │   ├── ubuntu.yml
│   │   └── v1.yml
│   ├── templates
│   │   └── nginx.conf.j2
│   ├── tests
│   │   ├── inventory
│   │   └── test.yml
│   └── vars
│       └── main.yml
├── README.md
└── second_run.txt


Ansible Run
-----------

I have run to time: ansible-playbook main.yml

for the first time the result is in first_run.txt:
	our node(nginx) returns the app version v2.0.0 because apps v3.0.0 and v4.0.0 return 500 as status code.
	                                --------------
for the send time the result is in second_run.txt:
	our node(nginx) returns the app version v3.0.0 because apps just v4.0.0 return 500 as status code.
					 -------------- 	
