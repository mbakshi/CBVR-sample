CBVR-sample
===========

Sample code for project Content Based Video Retrieval
This sample contains basic use of iterator functions and hash map properties to read and store the contents of the hash map in a file.

package VidRtrvl;

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;
import java.util.HashashOneap;
import java.util.Map;
import java.util.Properties;

public class dealName {
	
	private static Properties propFirst = new Properties();
	private static String file;
	
	dealName() {
		file = "";
	}
	
	dealName(String name) {
		file = name + "_stats";
	}
	
	public Map<String, Long> getName() {

		Map<String, Long> hashOne = new Hashmap<String, Long>();

		try {
			propFirst.load(new FileInputStream("D:\\576-multimedia\\project\\videos\\MeanTable"));

			for (String key : propFirst.stringPropertyNames()) {
				hashOne.put(key,
						Long.parseLong(propFirst.get(key).toString()));
			}
		} catch (FileNotFoundException e) {
			e.printStackTrace();
		} catch (IOException e) {
			e.printStackTrace();
		}

		return (hashOne);
	}

	public void addName(long mean) {
		Map<String, Long> hashOne = new Hashmap<String, Long>();
		try {
			propFirst.load(new FileInputStream("Absolute Path"));

			for (String key : propFirst.stringPropertyNames()) {
				hashOne.put(key, Long.parseLong(propFirst.get(key).toString()));
			}
			hashOne.put(file, mean);
			
			for (Map.Entry<String, Long> entry : hashOne.entrySet()) {
				propFirst.put(entry.getKey(),
						Long.toString(entry.getValue()));
			}
			propFirst.store(new FileOutputStream("Absolute Path"), null);
		} catch (FileNotFoundException e) {
			e.printStackTrace();
		} catch (IOException e) {
			e.printStackTrace();
		}
	}
}

