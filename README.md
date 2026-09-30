# scala
Practical No.1

object hello{
    def main(arg: Array[String]): Unit = {
        println("Welcome to SYDS!!!")
    }
}

Practical no.2

object maths {
    def main(args: Array[String]): Unit = {
        val a: Int = 20
        val b: Int = 5
        val marks: Double = 50.6
        val name: String = "Anu"
        val addition = a + b
        val subtraction = a - b
        val multiplication = a * b
        val division = a / b
        
        println("Name: " + name)
        println("First number: " + a)
        println("Second number: " + b)
        println("Marks: " + marks)
        println("Addition = " + addition)
        println("Subtraction = " + subtraction)
        println("Multiplication = " + multiplication)
        println("Division = " + division)
    }
}

Practical No.3

object stat {
    def main(args: Array[String]): Unit = {
        val data = Array(10, 20, 30, 20, 40)
        val mean = data.sum.toDouble / data.length
        val sorted = data.sorted
        val median = sorted(sorted.length / 2)
        val mode = data.groupBy(x => x).maxBy(x => x._2.length)._1
        
        println("Mean: " + mean)
        println("Median: " + median)
        println("Mode: " + mode)
    }
}

Practical No.4

object variance {
    def main(args: Array[String]): Unit = {
        val data = Array(10, 20, 30, 40, 50)
        val mean = data.sum.toDouble / data.length
        val variance = data.map(x => (x - mean) * (x - mean)).sum / data.length
        val standardDeviation = Math.sqrt(variance)
        
        println("Mean: " + mean)
        println("Variance: " + variance)
        println("Standard Deviation: " + standardDeviation)
    }
}

Practical no.5

write this code in "built.sbt" file:
val scala3Version = "3.8.4"

lazy val root = project
  .in(file("."))
  .settings(
    name := "scala3",
    version := "0.1.0-SNAPSHOT",

    scalaVersion := scala3Version,

    libraryDependencies += "org.scalameta" %% "munit" % "1.3.2" % Test,
    libraryDependencies += "org.scalanlp" %% "breeze" % "2.1.0"
  )

This is main file "breeze.scala":

import breeze.linalg._

object breeza{
    def main(args: Array[String]): Unit = {
        val v1 = DenseVector(1.0, 2.0, 3.0)
        val v2 = DenseVector(4.0, 5.0, 6.0)

        val sum = breeze.linalg.sum(v1)
        val mean = breeze.stats.mean(v1)
        val dotProduct = v1 dot v2

        println("Vector 1: " + v1)
        println("Vector 2: " + v2)
        println("Sum: " + sum)
        println("Mean: " + mean)
        println("Dot Product: " + dotProduct)
    }
}

















