# AI_Ancestry
The project lets users load a family tree
data file in JSON format, create a graph using Jaseci
with each person as a node and relationships as edges,
and visualize it in Jaseci Studio. Users can then use
Jaseci's simulation capabilities to analyze the graph and
explore family dynamics.

## Group Members
180356U - B.L.L.U. Liyanage<br>
180426K - P.M.T Nipuni<br>
180479A - N.K.P.N. Piyathissa<br>
180511R - R.P.A.C.M  Rajapaksha<br>
180586A - S.M.P. Senevirathne<br>

# Jaseci: Build the Next Generation of AI Products at Scale

<div style="display: flex; justify-content: center; align-items: center;">
  <img src="https://www.jaseci.org/wp-content/uploads/2022/02/jaseki-logo-inverted-rgb.svg" alt="Jaseci" width="50%" />
</div>

[![jaseci_core Unit Tests](https://github.com/Jaseci-Labs/jaseci/actions/workflows/jaseci-core-test.yml/badge.svg?branch=main)](https://github.com/Jaseci-Labs/jaseci/actions/workflows/jaseci-core-test.yml) [![PyPi version](https://badgen.net/pypi/v/jaseci/)](https://pypi.org/project/jaseci)
[![jaseci_serv Tests](https://github.com/Jaseci-Labs/jaseci/actions/workflows/jaseci-serv-test.yml/badge.svg)](https://github.com/Jaseci-Labs/jaseci/actions/workflows/jaseci-serv-test.yml) [![PyPi version](https://badgen.net/pypi/v/jaseci-serv/)](https://pypi.org/project/jaseci-serv)
[![Jac NLP](https://github.com/Jaseci-Labs/jaseci/actions/workflows/jac-nlp-test.yml/badge.svg?branch=main)](https://github.com/Jaseci-Labs/jaseci/actions/workflows/jac-nlp-test.yml)  [![PyPi version](https://badgen.net/pypi/v/jac_nlp/)](https://pypi.org/project/jac-nlp)
[![Jac Vision](https://github.com/Jaseci-Labs/jaseci/actions/workflows/jac-vision-test.yml/badge.svg?branch=main)](https://github.com/Jaseci-Labs/jaseci/actions/workflows/jac-vision-test.yml)  [![PyPi version](https://badgen.net/pypi/v/jac_vision/)](https://pypi.org/project/jac-vision)
[![Jac Speech](https://github.com/Jaseci-Labs/jaseci/actions/workflows/jac-speech-test.yml/badge.svg?branch=main)](https://github.com/Jaseci-Labs/jaseci/actions/workflows/jac-speech-test.yml)  [![PyPi version](https://badgen.net/pypi/v/jac_speech/)](https://pypi.org/project/jac-speech)
[![Jac Misc](https://github.com/Jaseci-Labs/jaseci/actions/workflows/jac-misc-test.yml/badge.svg?branch=main)](https://github.com/Jaseci-Labs/jaseci/actions/workflows/jac-misc-test.yml)  [![PyPi version](https://badgen.net/pypi/v/jac_misc/)](https://pypi.org/project/jac-misc)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

# New Feature - Identify Blood Group

## this function creates a report of same blood group
walker find_same_blood_group{
    has anchor same_blood_group = {};

    root: take-->node::family_root;
    family_root: take-->node::person;
    person {
        if (here.blood_group not in same_blood_group){
            same_blood_group[here.blood_group] = [];
        }
        same_blood_group[here.blood_group].l::append([here.name]);
    }
    with exit{
        std.out(same_blood_group);
        report same_blood_group; 
This code defines a function called find_same_blood_group that creates a report of people in a family who have the same blood group. The function uses a variable called same_blood_group to store a mapping between blood groups and a list of people who have that blood group.

The function starts by declaring the same_blood_group variable as an empty set. It then specifies that the root node of the family tree is the starting point for the traversal.

For each person in the family tree, the function checks whether their blood group is already present in the same_blood_group set. If not, it creates an empty list for that blood group. It then appends the person's name to the list associated with their blood group.

Finally, when the traversal of the family tree is complete, the function prints the same_blood_group variable to the standard output and returns it as the report.

The code assumes that the family tree is represented as a set of nested node objects, where each node object represents a person and contains attributes such as the person's name and blood group. However, it does not show how the family tree is constructed or how the node objects are defined.
