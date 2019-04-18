# Computer Graphics Homework 1

## First task

```C
for (int i = 0; i < (int)m.obj->numtriangles; i++) {
	...
}
```

This function responsible for storing the value of vertices and their colors.



## Second Task

```C
	for (int i = 0; i < m.obj->numtriangles * 3; i++)
	{
		//[TODO] Normalize each vertex value.
		m.vertices[3 * i + 2] = 1.0 * ((m.vertices[3 * i + 2] - meanVal[2]) / scale);
		m.vertices[3 * i + 1] = 1.0 * ((m.vertices[3 * i + 1] - meanVal[1]) / scale);
		m.vertices[3 * i + 0] = 1.0 * ((m.vertices[3 * i + 0] - meanVal[0]) / scale);
	}
```

Since the size of all of the objects varies. Therefore, we need to normalize all the size of the object into a predetermined size so there won't be any objects that look bigger than the other and vice versa.



## Third Task & Fourth Task

```C
void drawModel(model* model)
{
	//[TODO] Link vertex and color matrix to shader paremeter.
	//glVertexAttribPointer(???);
	//glVertexAttribPointer(???);
	glVertexAttribPointer(iLocPosition, 3, GL_FLOAT, GL_FALSE, 0, model->vertices);
	glVertexAttribPointer(iLocColor, 3, GL_FLOAT, GL_FALSE, 0, model->colors);

	//[TODO] Drawing command.
	//glDrawArrays(???);
	glDrawArrays(GL_TRIANGLES, 0, model->obj->numtriangles * 3);
}
```

This function has 2 responsibilities which are linking the vertices and their color together. While the other task is constructing the values in the array into recognizeable objects.



## Fifth Task

```C
void onKeyboard(unsigned char key, int x, int y)
{
	{
		...
		case 'c':
      //[TODO] Change polygon mode (GL_LINE or GL_FILL);
      use_wire_mode = !use_wire_mode;
      if (!use_wire_mode)
        glPolygonMode(GL_FRONT_AND_BACK, GL_FILL);
      else
        glPolygonMode(GL_FRONT_AND_BACK, GL_LINE);
      break;
	}
	...
}
```

In the beginning, we make sure that the displaying mode isn't in wire-framing mode. Later on, after execution is demanded, we have to check whether it's in wire-framing mode. If it isn't in wire-framing mode, wire-frame the object. If it is in wire-frame mode, set the display into normal mode.

