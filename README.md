import xml.etree.ElementTree as ET 
tree = ET.ElementTree(file="Task.xml")
root = tree.getroot()
page = input()
pose = input()
pages = root.findall('.//page[@name="'+page+'"]')
for page in pages:
    for steps in page:
        for step in steps:
            if step.attrib['frame']==pose:
                poselist=step.attrib['pose']
                poses=poselist.split()
                for values in poses:
                    print(values)
