# golang_beginner

# struct example
package main

import "fmt"

type Address struct {
    City, Ward string
}

type Parents struct {
	father, mother string 
}

type Person struct {
    Name    string
    Age     int
    Address Address
	Parents Parents
}

// Định nghĩa một phương thức cho struct Person
func (p Person) Greet() {
    fmt.Printf("Hello, my name is %s, I'm %d years old. \n I come from %s, %s. \n My father is %s and my mom is %s.\n", p.Name, p.Age, p.Address.City, p.Address.Ward, p.Parents.father, p.Parents.mother )
}

func main() {
    p := Person{
        Name: "Alice",
        Age:  30,
        Address: Address{
            City: "HCM",
            Ward: "TTN",
        },
		Parents: Parents{
			father:"henry",
			mother:"merry",
		},
    }
    p.Greet()
}
