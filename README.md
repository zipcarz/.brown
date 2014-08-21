.brown
======
              << " arguments:" << arguments;
	 
Base* object = GetApiObject(object_id);
-  LOG(WARNING) << "Unknown object: " << object_id
+  if (object)
+    object->CallSync(method, arguments, result);
+  else
+    DLOG(WARNING) << "Unknown object: " << object_id
<< " type:" << type
 << " method:" << method
  << " arguments:" << arguments;
-  if (object)
-    object->CallSync(method, arguments, result);
	 }
void DispatcherHost::OnCallStaticMethod(
