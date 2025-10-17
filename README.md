import React, { useState } from "react";

function AttendanceTracker() {
  const students = ["Ravi", "Anita", "Karan", "Meena", "Rohit"];
  const [present, setPresent] = useState([]);

  const handleChange = (name) => {
    if (present.includes(name)) {
      setPresent(present.filter((n) => n !== name));
    } else {
      setPresent([...present, name]);
    }
  };

  return (
    <div>
      <h2>Attendance Tracker</h2>
      {students.map((name) => (
        <div key={name}>
          <label>
            <input
              type="checkbox"
              checked={present.includes(name)}
              onChange={() => handleChange(name)}
            />
            {name}
          </label>
        </div>
      ))}
      <p>
        Total Present: {present.length} / {students.length}
      </p>
    </div>
  );
}

export default AttendanceTracker;
