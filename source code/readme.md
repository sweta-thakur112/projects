!pip install docx2txt
import docx2txt
!pip install sklearn
job_dis=docx2txt.process('/content/Sample Job Description.docx')
resume=docx2txt.process('/content/VIKASH.docx')
content=[job_dis,resume]
from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()
matrix=cv.fit_transform(content)
from sklearn.metrics.pairwise import cosine_similarity
similarity_matrix=cosine_similarity(matrix)
print('resume matches by' +" "+ str(similarity_matrix[0][1]*100)+"%")
