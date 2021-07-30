Name : Johni Yoods Durai

email : durai.mj@mistralsolutions.com

notebook :https://colab.research.google.com/drive/1ZSu41eW6TPDxUPXXD75gc68QfVs0REnS?usp=sharing

# Session 12
# Sequence Types


### Lazy Polygon 
1. A regular strictly convex polygon is a polygon that has the following characteristics:
   1. all interior angles are less than 180
   2. all sides have equal length
2. For a regular strictly convex polygon with:
   1. n edges (=n vertices)
   2. R circumradius
   3. interiorAngle = (n-2)*180/n
   4. edgeLength, s = 2*R*sin(pi/n)
   5. apothem, a= R*cos(pi/n)
   6. area = 1/2*n*s*a
   7. perimeter = n*s



To create lazy polgon class the following support has added

###   def __iter__(self):
        return self.Polygon(self._m,self._R,self)

###      def __next__(self):
            if self._index >= len(self._obj):
                raise StopIteration
            else:
                item = self._obj.Polygon(self._index,self._R,self._obj)
                self._index += 1
                return item


### Sample output
    pol = Polygons(10,4)
    fact_iter = iter(pol)
    for _ in range(5):
        print(next(fact_iter))
    
Polygon(n=3, R=4)
Polygon(n=4, R=4)
Polygon(n=5, R=4)
Polygon(n=6, R=4)
Polygon(n=7, R=4)
