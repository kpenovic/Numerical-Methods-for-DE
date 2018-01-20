**Routine Name:**           machineEpsilon

**Author:** Kegan Penovich

**Language:** Python.

**Description/Purpose:** This routine will compute the single precision value for the machine epsilon or the number of digits
in the representation of real numbers in single precision. This is a routine for analyzing the behavior of any computer. This
usually will need to be run one time for each computer.

**Input:** The imput is the type of float which you would like to find the machine epsilon for. numpy.float32 for 32 bit and numpy.float64 for 64 bit.

**Output:** This routine returns a float that represent an upper bound on the reletive error due to rounding in floating point arithmetic.

**Usage/Example:**

The routine need only be called and given the particular float type you are looking for.

      import numpy
      
      machineEpsilon(numpy.float32)
      machineEpsilon(numpy.float64)

Output from the lines above:

      1.19209e-07
      2.22044604925e-16

The function can be called without importing numpy and the result will be for the default float setting for the machine.

**Implementation/Code:** The following is the code for smaceps()

    def machineEpsilon(numType=float): 
            #This declairs the number 1 in whatever version of float you are choosing to use
        machine_epsilon = numType(1)
            #We will now divide 1 by two and then add that back to one.
            #If the result cannot be differeniated from one, then the previous value added would be the smallest
            #number that the machine can identify. We call this our machine epsilon.
        while numType(1)+numType(machine_epsilon) != numType(1):
            machine_epsilon_last = machine_epsilon
            machine_epsilon = numType(machine_epsilon) / numType(2)
        return machine_epsilon_last

**Last Modified:** January/2018
