## C++ 合并文件

```
   const string workspace =  "";
	const string outputfilename = "";
	const string prefix = "";
	const int filenum = ;
	string buf;
	buf.resize(600);
	fstream file(outputfilename, ios::binary | ios::out);
	if (!file.is_open())
	{
		cout << "cannot open the file: " << outputfilename << endl;
		exit(-1);
	}
	for (int i = 0; i <= filenum; i++)
	{
		string currentfile = workspace + prefix + to_string(i);
		fstream inputfilename(currentfile, ios::in | ios::binary);
		if (!inputfilename.is_open())
		{
			cout << "cannot open the file: " << currentfile << endl;
			exit(-1);
		}
		while (!inputfilename.eof())
		{
			getline(inputfilename, buf);
			file << buf;
			file << endl;
		}
		inputfilename.close();
	}
	file.close();
```
