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

# Định nghĩa một phương thức cho struct Person
func (p Person) Greet() {
    fmt.Printf("Hello, my name is %s, I'm %d years old. \n I come from %s, %s. \n My father is %s and my mom is %s.\n", p.Name, p.Age, p.Address.City, p.Address.Ward, p.Parents.father, p.Parents.mother )
}
# Run program
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

# Vòng lặp for

package main

import "fmt"

func main() {
    sum := 1

    // Vòng lặp for vô hạn
    for {
        sum += sum // Cộng sum vào chính nó
        if sum > 1000 {
            break // Thoát khỏi vòng lặp khi sum lớn hơn 1000
        }
    }

    fmt.Println("Tổng:", sum) // Output: Tổng: 1024
}
# vòng lặp trong slice
package main

import "fmt"

func main() {
    nums := []int{2, 4, 6, 8, 10}

    // Vòng lặp for với range để lặp qua các phần tử của slice
    for index, value := range nums {
        fmt.Printf("Index: %d, Value: %d\n", index, value)
    }
}

# Methods and pointer indirection
package main

import "fmt"

type Vertex struct {
	X, Y float64
}

func (v *Vertex) Scale(f float64) {
	v.X = v.X * f
	v.Y = v.Y * f
}

func ScaleFunc(v *Vertex, f float64) {
	v.X = v.X * f
	v.Y = v.Y * f
}

func main() {
	v := Vertex{3, 4}
	v.Scale(2)
	ScaleFunc(&v, 10)

	p := &Vertex{4, 3}
	p.Scale(3)
	ScaleFunc(p, 8)

	fmt.Println(v, p)
}

