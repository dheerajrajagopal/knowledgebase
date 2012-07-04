#! /usr/bin/env python

import sqlite3 

con = sqlite3.connect('knowlegebase.db')
cur = con.cursor()

class Concept:
	
	def __init__(self, concept1):
		self.concept1 = concept1 


	def select_concept2 (self) :
		print self.concept1
		concept1_tuple = cur.execute("select id from concept_concept1 where concept_name = :concept_name", {"concept_name":self.concept1} )
		for i in concept1_tuple:
			concept1_id = i[0] - 1
		
		print concept1_id
		
		concept2_list = cur.execute(" select concept2_id, score, correctness from concept_tuple where concept1_id = :concept1_id", {"concept1_id": concept1_id} )

		concept2_id = []
		score = []
		correctness = []
		
		for i in concept2_list:
			concept2_id.append(i[0])
			score.append(i[1])
			correctness.append(i[2])
		
		
		concept2 = []

		for i in concept2_id:
			c = cur.execute("select concept_name from concept_concept2 where id = :id", {"id":i})
			for i in c:
				concept2.append(i[0])

		tuples = []
		
		for i in range(len(concept2)):
			t = ( concept2[i], score[i], correctness[i] )
			tuples.append(t)

		return tuples


	def all_concept1(self):
		
		concept1_all = cur.execute("select concept_name from concept_concept1")
		conc1 = []
		for i in concept1_all:
			conc1.append(i[0])	

		return conc1



k = Concept("plate")

l = k.select_concept2()

m = k.all_concept1()


print l 

print m


cur.close()

